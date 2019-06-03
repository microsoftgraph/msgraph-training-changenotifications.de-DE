<!-- markdownlint-disable MD002 MD041 -->

Abonnements für Benachrichtigungen laufen ab und müssen regelmäßig erneuert werden.

Öffnen Sie **NotificationsController.cs** , und `Get()` ersetzen Sie die-Methode durch den folgenden Code:

```csharp
private static Dictionary<string, Subscription> Subscriptions = new Dictionary<string, Subscription>();
private static Timer subscriptionTimer = null;

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

Fügen Sie die folgende using-Anweisung am Anfang der Datei hinzu.

```csharp
using System.Threading;
```

In diesem obigen Code wird ein Hintergrund-Timer hinzugefügt, der alle 15 Sekunden abgefeuert wird und Abonnements überprüft, um zu sehen, ob Sie abgelaufen sind.

Fügen Sie die folgenden neuen Methoden hinzu:

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

Die `CheckSubscriptions` Methode wird vom Timer alle 15 Sekunden aufgerufen. Für die Verwendung in der Produktion sollte dies auf einen vernünftigeren Wert festgelegt werden, um die Anzahl unnötiger Aufrufe von Graph zu reduzieren. Die `RenewSubscription` Methode erneuert ein Abonnement und wird nur aufgerufen, wenn ein Abonnement in den nächsten zwei Minuten abläuft.

Wählen Sie **Debug #a0 Debuggen starten** aus, um die Anwendung auszuführen. Navigieren Sie zur folgenden URL `*http://localhost:5000/api/notifications` , um ein neues Abonnement zu registrieren.

Die folgende Ausgabe wird im `DEBUG OUTPUT` Fenster mit Visual Studio Code ungefähr alle 15 Sekunden angezeigt.  Dies ist der Zeitgeber, der das Abonnement auf Ablauf überprüft.

```shell
Checking subscriptions 12:32:51.882
Current subscription count 1
```

Warten Sie einige Minuten, und Sie sehen Folgendes, wenn das Abonnement erneuert werden muss:

```shell
Renewed subscription: 07ca62cd-1a1b-453c-be7b-4d196b3c6b5b, New Expiration: 3/10/2019 7:43:22 PM +00:00
```

Dies deutet darauf hin, dass das Abonnement erneuert wurde, und zeigt die neue Ablaufzeit an.
