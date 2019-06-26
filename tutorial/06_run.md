<!-- markdownlint-disable MD002 MD041 -->

<span data-ttu-id="5218b-101">Erstellen Sie eine Startkonfiguration, um die Anwendung in Visual Studio Code zu debuggen.</span><span class="sxs-lookup"><span data-stu-id="5218b-101">Create a launch configuration to debug the application in Visual Studio Code.</span></span>

<span data-ttu-id="5218b-102">Wählen Sie in Visual Studio Code die Option **Debug #a0 Open Configurations**aus.</span><span class="sxs-lookup"><span data-stu-id="5218b-102">Within Visual Studio Code, select **Debug > Open Configurations**.</span></span>

  ![Screencast von vs-Code zum Öffnen von Startkonfigurationen](./images/vscode-debugapp-01.png)

<span data-ttu-id="5218b-104">Wenn Sie zur Auswahl einer Umgebung aufgefordert werden, wählen Sie **.net Core**aus.</span><span class="sxs-lookup"><span data-stu-id="5218b-104">When prompted to select an environment, select **.NET Core**.</span></span>

  ![Screencast von vs-Code erstellen einer Startkonfiguration für .net Core](./images/vscode-debugapp-02.png)

> [!NOTE]
> <span data-ttu-id="5218b-106">Standardmäßig wird die .net Core-Startkonfiguration einen Browser öffnen und zur Standard-URL für die Anwendung navigieren, wenn der Debugger gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="5218b-106">By default, the .NET Core launch configuration will open a browser and navigate to the default URL for the application when launching the debugger.</span></span> <span data-ttu-id="5218b-107">Für diese Anwendung möchten wir stattdessen zur NGrok-URL navigieren.</span><span class="sxs-lookup"><span data-stu-id="5218b-107">For this application, we instead want to navigate to the NGrok URL.</span></span> <span data-ttu-id="5218b-108">Wenn Sie die Startkonfiguration unverändert lassen, wird jedes Mal, wenn Sie die Anwendung debuggen, eine fehlerhafte Seite angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5218b-108">If you leave the launch configuration as is, each time you debug the application it will display a broken page.</span></span> <span data-ttu-id="5218b-109">Sie können die URL einfach ändern oder die Startkonfiguration so ändern, dass der Browser nicht gestartet wird:</span><span class="sxs-lookup"><span data-stu-id="5218b-109">You can just change the URL, or change the launch configuration to not launch the browser:</span></span>

<span data-ttu-id="5218b-110">Aktualisieren der Startkonfiguration für Visual Studio Debugger:</span><span class="sxs-lookup"><span data-stu-id="5218b-110">Update the Visual Studio debugger launch configuration:</span></span>

  1. <span data-ttu-id="5218b-111">Öffnen Sie in Visual Studio Code die Datei **. vscode/Launch. JSON**.</span><span class="sxs-lookup"><span data-stu-id="5218b-111">In Visual Studio Code, open the file **.vscode/launch.json**.</span></span>
  1. <span data-ttu-id="5218b-112">Suchen Sie den folgenden Abschnitt in der Standardkonfiguration:</span><span class="sxs-lookup"><span data-stu-id="5218b-112">Locate the following section in the default configuration:</span></span>

      ```json
      "launchBrowser": {
        "enabled": true
      },
      ```

  1. <span data-ttu-id="5218b-113">Legen Sie `enabled` die- `false`Eigenschaft auf fest.</span><span class="sxs-lookup"><span data-stu-id="5218b-113">Set the `enabled` property to `false`.</span></span>
  1. <span data-ttu-id="5218b-114">Speichern Sie Ihre Änderungen.</span><span class="sxs-lookup"><span data-stu-id="5218b-114">Save your changes.</span></span>

### <a name="test-the-application"></a><span data-ttu-id="5218b-115">Testen Sie die Anwendung:</span><span class="sxs-lookup"><span data-stu-id="5218b-115">Test the application:</span></span>

<span data-ttu-id="5218b-116">Klicken Sie in Visual Studio Code auf **Debuggen #a0 Debuggen starten** , um die Anwendung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="5218b-116">In Visual Studio Code, select **Debug > Start debugging** to run the application.</span></span> <span data-ttu-id="5218b-117">Im vs-Code wird die Anwendung erstellt und gestart.</span><span class="sxs-lookup"><span data-stu-id="5218b-117">VS Code will build and star the application.</span></span>

<span data-ttu-id="5218b-118">Wenn im Fenster **Debug Console** Folgendes angezeigt wird...</span><span class="sxs-lookup"><span data-stu-id="5218b-118">Once you see the following in the **Debug Console** window...</span></span>

![Screenshot der vs-Code-Debug-Konsole](./images/vscode-debugapp-03.png)

<span data-ttu-id="5218b-120">... Öffnen Sie einen Browser, und **http://localhost:5000/api/notifications** navigieren Sie zu, um Änderungsbenachrichtigungen zu abonnieren.</span><span class="sxs-lookup"><span data-stu-id="5218b-120">... open a browser and navigate to **http://localhost:5000/api/notifications** to subscribe to change notifications.</span></span> <span data-ttu-id="5218b-121">Bei erfolgreicher Ausführung wird eine Ausgabe mit einer Abonnement-ID wie die folgende angezeigt:</span><span class="sxs-lookup"><span data-stu-id="5218b-121">If successful you will see output that includes a subscription id like the one below:</span></span>

![Screenshot eines erfolgreichen Abonnements](./images/vscode-debugapp-04.png)

<span data-ttu-id="5218b-123">Ihre Anwendung abonniert jetzt Benachrichtigungen von Microsoft Graph, wenn ein Update für alle Benutzer im Office 365 Mandanten vorgenommen wird.</span><span class="sxs-lookup"><span data-stu-id="5218b-123">Your application is now subscribed to receive notifications from the Microsoft Graph when an update is made on any users in the Office 365 tenant.</span></span>

<span data-ttu-id="5218b-124">Eine Benachrichtigung auslösen:</span><span class="sxs-lookup"><span data-stu-id="5218b-124">Trigger a notification:</span></span>

1. <span data-ttu-id="5218b-125">Öffnen Sie einen Browser, und navigieren Sie zum [Microsoft 365 adminhttps://admin.microsoft.com/AdminPortal)Center (](https://admin.microsoft.com/AdminPortal).</span><span class="sxs-lookup"><span data-stu-id="5218b-125">Open a browser and navigate to the [Microsoft 365 admin center (https://admin.microsoft.com/AdminPortal)](https://admin.microsoft.com/AdminPortal).</span></span>
1. <span data-ttu-id="5218b-126">Wenn Sie zur Anmeldung aufgefordert werden, melden Sie sich mit einem Administratorkonto an.</span><span class="sxs-lookup"><span data-stu-id="5218b-126">If prompted to login, sign-in using an admin account.</span></span>
1. <span data-ttu-id="5218b-127">Wählen Sie **Benutzer #a0 aktive Benutzer**aus.</span><span class="sxs-lookup"><span data-stu-id="5218b-127">Select **Users > Active users**.</span></span>

    ![Screenshot des Microsoft 365 Admin Center](./images/vscode-debugapp-05.png)

1. <span data-ttu-id="5218b-129">Wählen Sie einen aktiven Benutzer aus, und wählen Sie **Bearbeiten** als **Kontaktinformationen**aus.</span><span class="sxs-lookup"><span data-stu-id="5218b-129">Select an active user and select **Edit** for their **Contact information**.</span></span>

    ![Screenshot der Details eines Benutzers](./images/vscode-debugapp-06.png)

1. <span data-ttu-id="5218b-131">Aktualisieren Sie den Wert der **Telefonnummer** mit einer neuen Nummer, und wählen Sie **Speichern**aus.</span><span class="sxs-lookup"><span data-stu-id="5218b-131">Update the **Phone number** value with a new number and Select **Save**.</span></span>

    <span data-ttu-id="5218b-132">In der Visual Studio-Code- **Debug-Konsole**wird eine Benachrichtigung empfangen.</span><span class="sxs-lookup"><span data-stu-id="5218b-132">In the Visual Studio Code **Debug Console**, you will see a notification has been received.</span></span> <span data-ttu-id="5218b-133">Manchmal kann es einige Minuten dauern, bis Sie eintreffen.</span><span class="sxs-lookup"><span data-stu-id="5218b-133">Sometimes this may take a few minutes to arrive.</span></span> <span data-ttu-id="5218b-134">Ein Beispiel für die Ausgabe ist unten:</span><span class="sxs-lookup"><span data-stu-id="5218b-134">An example of the output is below:</span></span>

    ```shell
    Received notification: 'Users/7a7fded6-0269-42c2-a0be-512d58da4463', 7a7fded6-0269-42c2-a0be-512d58da4463
    ```

<span data-ttu-id="5218b-135">Dadurch wird angegeben, dass die Anwendung die Benachrichtigung vom Microsoft Graph erfolgreich für den in der Ausgabe angegebenen Benutzer erhalten hat.</span><span class="sxs-lookup"><span data-stu-id="5218b-135">This indicates the application successfully received the notification from the Microsoft Graph for the user specified in the output.</span></span> <span data-ttu-id="5218b-136">Anschließend können Sie diese Informationen verwenden, um die Microsoft Graph-Daten für die Benutzer vollständig abzufragen, wenn Sie Ihre Details in Ihrer Anwendung synchronisieren möchten.</span><span class="sxs-lookup"><span data-stu-id="5218b-136">You can then use this information to query the Microsoft Graph for the users full details if you want to synchronize their details into your application.</span></span>