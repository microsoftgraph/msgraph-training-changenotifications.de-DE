<!-- markdownlint-disable MD002 MD041 -->

<span data-ttu-id="e0144-101">Abonnements für Benachrichtigungen laufen ab und müssen regelmäßig erneuert werden.</span><span class="sxs-lookup"><span data-stu-id="e0144-101">Subscriptions for notifications expire and need to be renewed periodically.</span></span> <span data-ttu-id="e0144-102">In den folgenden Schritten wird gezeigt, wie Sie Benachrichtigungen erneuern.</span><span class="sxs-lookup"><span data-stu-id="e0144-102">The following steps will demonstrate how to renew notifications</span></span>

<span data-ttu-id="e0144-103">Öffnen von **Controllern #a0 NotificationsController.cs** -Datei</span><span class="sxs-lookup"><span data-stu-id="e0144-103">Open **Controllers > NotificationsController.cs** file</span></span>

<span data-ttu-id="e0144-104">Fügen Sie der `NotificationsController` -Klasse die folgenden zwei Member-Deklarationen hinzu:</span><span class="sxs-lookup"><span data-stu-id="e0144-104">Add the following two member declarations to the `NotificationsController` class:</span></span>

```csharp
private static Dictionary<string, Subscription> Subscriptions = new Dictionary<string, Subscription>();
private static Timer subscriptionTimer = null;
```

<span data-ttu-id="e0144-105">Fügen Sie die folgenden neuen Methoden hinzu.</span><span class="sxs-lookup"><span data-stu-id="e0144-105">Add the following new methods.</span></span> <span data-ttu-id="e0144-106">Dadurch wird ein Hintergrund-Timer implementiert, der alle 15 Sekunden ausgeführt wird, um zu überprüfen, ob Abonnements abgelaufen sind.</span><span class="sxs-lookup"><span data-stu-id="e0144-106">These will implement a background timer that will run every 15 seconds to check if subscriptions have expired.</span></span> <span data-ttu-id="e0144-107">Wenn dies der Fall ist, werden Sie erneuert.</span><span class="sxs-lookup"><span data-stu-id="e0144-107">If they have, they will be renewed.</span></span>

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

<span data-ttu-id="e0144-108">Die `CheckSubscriptions` Methode wird vom Timer alle 15 Sekunden aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="e0144-108">The `CheckSubscriptions` method is called every 15 seconds by the timer.</span></span> <span data-ttu-id="e0144-109">Für die Produktions Verwendung sollte dies auf einen vernünftigeren Wert festgelegt werden, um die Anzahl unnötiger Aufrufe von Microsoft Graph zu reduzieren.</span><span class="sxs-lookup"><span data-stu-id="e0144-109">For production use this should be set to a more reasonable value to reduce the number of unnecessary calls to Microsoft Graph.</span></span>

<span data-ttu-id="e0144-110">Die `RenewSubscription` Methode erneuert ein Abonnement und wird nur aufgerufen, wenn ein Abonnement in den nächsten zwei Minuten abläuft.</span><span class="sxs-lookup"><span data-stu-id="e0144-110">The `RenewSubscription` method renews a subscription and is only called if a subscription is going to expire in the next two minutes.</span></span>

<span data-ttu-id="e0144-111">Suchen Sie die `Get()` -Methode, und ersetzen Sie Sie durch den folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="e0144-111">Locate the method `Get()` and replace it with the following code:</span></span>

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

<span data-ttu-id="e0144-112">Fügen Sie die folgende Anweisung nach den `using` vorhandenen Anweisungen am Anfang der Datei hinzu:</span><span class="sxs-lookup"><span data-stu-id="e0144-112">Add the following statement after the existing `using` statements at the top of the file:</span></span>

```csharp
using System.Threading;
```

### <a name="test-the-changes"></a><span data-ttu-id="e0144-113">Testen Sie die Änderungen:</span><span class="sxs-lookup"><span data-stu-id="e0144-113">Test the changes:</span></span>

<span data-ttu-id="e0144-114">Wählen Sie in Visual Studio Code Debuggen aus, um die Anwendung mit dem **Debuggen #a0 starten** .</span><span class="sxs-lookup"><span data-stu-id="e0144-114">Within Visual Studio Code, select **Debug > Start debugging** to run the application.</span></span>
<span data-ttu-id="e0144-115">Navigieren Sie zur folgenden URL: **http://localhost:5000/api/notifications**.</span><span class="sxs-lookup"><span data-stu-id="e0144-115">Navigate to the following url: **http://localhost:5000/api/notifications**.</span></span> <span data-ttu-id="e0144-116">Dadurch wird ein neues Abonnement registriert.</span><span class="sxs-lookup"><span data-stu-id="e0144-116">This will register a new subscription.</span></span>

<span data-ttu-id="e0144-117">Beachten Sie im Fenster Visual Studio- **Debug-Konsole** etwa alle 15 Sekunden den Zeit Geber, der das Abonnement auf Ablauf überprüft:</span><span class="sxs-lookup"><span data-stu-id="e0144-117">In the Visual Studio Code **Debug Console** window, approximately every 15 seconds, notice the timer checking the subscription for expiration:</span></span>

```shell
Checking subscriptions 12:32:51.882
Current subscription count 1
```

<span data-ttu-id="e0144-118">Warten Sie einige Minuten, und Sie sehen Folgendes, wenn das Abonnement erneuert werden muss:</span><span class="sxs-lookup"><span data-stu-id="e0144-118">Wait a few minutes and you will see the following when the subscription needs renewing:</span></span>

```shell
Renewed subscription: 07ca62cd-1a1b-453c-be7b-4d196b3c6b5b, New Expiration: 3/10/2019 7:43:22 PM +00:00
```

<span data-ttu-id="e0144-119">Dies deutet darauf hin, dass das Abonnement erneuert wurde, und zeigt die neue Ablaufzeit an.</span><span class="sxs-lookup"><span data-stu-id="e0144-119">This indicates that the subscription was renewed and shows the new expiry time.</span></span>