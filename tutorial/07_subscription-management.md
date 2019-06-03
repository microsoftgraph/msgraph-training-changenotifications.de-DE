<!-- markdownlint-disable MD002 MD041 -->

<span data-ttu-id="7722b-101">Abonnements für Benachrichtigungen laufen ab und müssen regelmäßig erneuert werden.</span><span class="sxs-lookup"><span data-stu-id="7722b-101">Subscriptions for notifications expire and need to be renewed periodically.</span></span>

<span data-ttu-id="7722b-102">Öffnen Sie **NotificationsController.cs** , und `Get()` ersetzen Sie die-Methode durch den folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="7722b-102">Open **NotificationsController.cs** and replace the `Get()` method with the following code:</span></span>

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

<span data-ttu-id="7722b-103">Fügen Sie die folgende using-Anweisung am Anfang der Datei hinzu.</span><span class="sxs-lookup"><span data-stu-id="7722b-103">Add the following using statement at the top of the file.</span></span>

```csharp
using System.Threading;
```

<span data-ttu-id="7722b-104">In diesem obigen Code wird ein Hintergrund-Timer hinzugefügt, der alle 15 Sekunden abgefeuert wird und Abonnements überprüft, um zu sehen, ob Sie abgelaufen sind.</span><span class="sxs-lookup"><span data-stu-id="7722b-104">This code above adds a background timer that will fire every 15 seconds and check subscriptions to see if they have expired.</span></span>

<span data-ttu-id="7722b-105">Fügen Sie die folgenden neuen Methoden hinzu:</span><span class="sxs-lookup"><span data-stu-id="7722b-105">Add the following new methods:</span></span>

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

<span data-ttu-id="7722b-106">Die `CheckSubscriptions` Methode wird vom Timer alle 15 Sekunden aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="7722b-106">The `CheckSubscriptions` method is called every 15 seconds by the timer.</span></span> <span data-ttu-id="7722b-107">Für die Verwendung in der Produktion sollte dies auf einen vernünftigeren Wert festgelegt werden, um die Anzahl unnötiger Aufrufe von Graph zu reduzieren.</span><span class="sxs-lookup"><span data-stu-id="7722b-107">For production use this should be set to a more reasonable value to reduce the number of unnecessary calls to Graph.</span></span> <span data-ttu-id="7722b-108">Die `RenewSubscription` Methode erneuert ein Abonnement und wird nur aufgerufen, wenn ein Abonnement in den nächsten zwei Minuten abläuft.</span><span class="sxs-lookup"><span data-stu-id="7722b-108">The `RenewSubscription` method renews a subscription and is only called if a subscription is going to expire in the next two minutes.</span></span>

<span data-ttu-id="7722b-109">Wählen Sie **Debug #a0 Debuggen starten** aus, um die Anwendung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="7722b-109">Select **Debug > Start debugging** to run the application.</span></span> <span data-ttu-id="7722b-110">Navigieren Sie zur folgenden URL `*http://localhost:5000/api/notifications` , um ein neues Abonnement zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="7722b-110">Navigate to the following url `*http://localhost:5000/api/notifications` to register a new subscription.</span></span>

<span data-ttu-id="7722b-111">Die folgende Ausgabe wird im `DEBUG OUTPUT` Fenster mit Visual Studio Code ungefähr alle 15 Sekunden angezeigt.</span><span class="sxs-lookup"><span data-stu-id="7722b-111">You will see the following output in the `DEBUG OUTPUT` window of Visual Studio Code approximately every 15 seconds.</span></span>  <span data-ttu-id="7722b-112">Dies ist der Zeitgeber, der das Abonnement auf Ablauf überprüft.</span><span class="sxs-lookup"><span data-stu-id="7722b-112">This is the timer checking the subscription for expiry.</span></span>

```shell
Checking subscriptions 12:32:51.882
Current subscription count 1
```

<span data-ttu-id="7722b-113">Warten Sie einige Minuten, und Sie sehen Folgendes, wenn das Abonnement erneuert werden muss:</span><span class="sxs-lookup"><span data-stu-id="7722b-113">Wait a few minutes and you will see the following when the subscription needs renewing:</span></span>

```shell
Renewed subscription: 07ca62cd-1a1b-453c-be7b-4d196b3c6b5b, New Expiration: 3/10/2019 7:43:22 PM +00:00
```

<span data-ttu-id="7722b-114">Dies deutet darauf hin, dass das Abonnement erneuert wurde, und zeigt die neue Ablaufzeit an.</span><span class="sxs-lookup"><span data-stu-id="7722b-114">This indicates that the subscription was renewed and shows the new expiry time.</span></span>
