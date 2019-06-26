<!-- markdownlint-disable MD002 MD041 -->

Abonnements für Benachrichtigungen laufen ab und müssen regelmäßig erneuert werden. In den folgenden Schritten wird gezeigt, wie Sie Benachrichtigungen erneuern.

Öffnen von **Controllern #a0 NotificationsController.cs** -Datei

Fügen Sie der `NotificationsController` -Klasse die folgenden zwei Member-Deklarationen hinzu:

```csharp
private static Dictionary<string, Subscription> Subscriptions = new Dictionary<string, Subscription>();
private static Timer subscriptionTimer = null;
```

Fügen Sie die folgenden neuen Methoden hinzu. Dadurch wird ein Hintergrund-Timer implementiert, der alle 15 Sekunden ausgeführt wird, um zu überprüfen, ob Abonnements abgelaufen sind. Wenn dies der Fall ist, werden Sie erneuert.

```csharp
private void CheckSubscriptions(Object stateInfo)
{
  AutoResetEvent autoEvent = (AutoResetEvent)stateInfo;

  Console.WriteLine($"Checking subscriptions {DateTime.Now.ToString("h:mm:ss.fff")}");
  Console.WriteLine($"Current subscription count {Subscriptions.Count()}");

  foreach(var subscription in Subscriptions)
  {
    // if the subscription expires in the next 2 min, renew it
    if(subscription.Value.ExpirationDateTime < DateTime.UtcNow.AddMinutes(2))
    {
      RenewSubscription(subscription.Value);
    }
  }
}

private void RenewSubscription(Subscription subscription)
{
  Console.WriteLine($"Current subscription: {subscription.Id}, Expiration: {subscription.ExpirationDateTime}");

  var graphServiceClient = GetGraphClient();

  subscription.ExpirationDateTime = DateTime.UtcNow.AddMinutes(5);

  var foo = graphServiceClient
    .Subscriptions[subscription.Id]
    .Request()
    .UpdateAsync(subscription).Result;

  Console.WriteLine($"Renewed subscription: {subscription.Id}, New Expiration: {subscription.ExpirationDateTime}");
}
```

Die `CheckSubscriptions` Methode wird vom Timer alle 15 Sekunden aufgerufen. Für die Produktions Verwendung sollte dies auf einen vernünftigeren Wert festgelegt werden, um die Anzahl unnötiger Aufrufe von Microsoft Graph zu reduzieren.

Die `RenewSubscription` Methode erneuert ein Abonnement und wird nur aufgerufen, wenn ein Abonnement in den nächsten zwei Minuten abläuft.

Suchen Sie die `Get()` -Methode, und ersetzen Sie Sie durch den folgenden Code:

```csharp
[HttpGet]
public ActionResult<string> Get()
{
    var graphServiceClient = GetGraphClient();

    var sub = new Microsoft.Graph.Subscription();
    sub.ChangeType = "updated";
    sub.NotificationUrl = config.Ngrok + "/api/notifications";
    sub.Resource = "/users";
    sub.ExpirationDateTime = DateTime.UtcNow.AddMinutes(5);
    sub.ClientState = "SecretClientState";

    var newSubscription = graphServiceClient
      .Subscriptions
      .Request()
      .AddAsync(sub).Result;

    Subscriptions[newSubscription.Id] = newSubscription;

    if(subscriptionTimer == null)
    {
        subscriptionTimer = new Timer(CheckSubscriptions, null, 5000, 15000);
    }

    return $"Subscribed. Id: {newSubscription.Id}, Expiration: {newSubscription.ExpirationDateTime}";
}
```

Fügen Sie die folgende Anweisung nach den `using` vorhandenen Anweisungen am Anfang der Datei hinzu:

```csharp
using System.Threading;
```

### <a name="test-the-changes"></a>Testen Sie die Änderungen:

Wählen Sie in Visual Studio Code Debuggen aus, um die Anwendung mit dem **Debuggen #a0 starten** .
Navigieren Sie zur folgenden URL: **http://localhost:5000/api/notifications**. Dadurch wird ein neues Abonnement registriert.

Beachten Sie im Fenster Visual Studio- **Debug-Konsole** etwa alle 15 Sekunden den Zeit Geber, der das Abonnement auf Ablauf überprüft:

```shell
Checking subscriptions 12:32:51.882
Current subscription count 1
```

Warten Sie einige Minuten, und Sie sehen Folgendes, wenn das Abonnement erneuert werden muss:

```shell
Renewed subscription: 07ca62cd-1a1b-453c-be7b-4d196b3c6b5b, New Expiration: 3/10/2019 7:43:22 PM +00:00
```

Dies deutet darauf hin, dass das Abonnement erneuert wurde, und zeigt die neue Ablaufzeit an.