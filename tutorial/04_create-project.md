<!-- markdownlint-disable MD002 MD041 -->

<span data-ttu-id="bfc3e-101">Öffnen Sie die Eingabeaufforderung, navigieren Sie zu einem Verzeichnis, in dem Sie über Rechte zum Erstellen Ihres Projekts verfügen, und führen Sie den folgenden Befehl aus, um eine neue .net Core-WebApi-APP zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="bfc3e-101">Open your command prompt, navigate to a directory where you have rights to create your project, and run the following command to create a new .NET Core WebApi app:</span></span>

```shell
dotnet new webapi -o msgraphapp
```

<span data-ttu-id="bfc3e-102">Führen Sie nach dem Erstellen der Anwendung die folgenden Befehle aus, um sicherzustellen, dass das neue Projekt ordnungsgemäß ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="bfc3e-102">After creating the application, run the following commands to ensure your new project runs correctly.</span></span>

  ```shell
  cd msgraphapp
  dotnet add package Microsoft.Identity.Client
  dotnet add package Microsoft.Graph
  dotnet run
  ```

  <span data-ttu-id="bfc3e-103">Die Anwendung wird Folgendes starten und ausgeben:</span><span class="sxs-lookup"><span data-stu-id="bfc3e-103">The application will start and output the following:</span></span>

  ```shell
  info: Microsoft.AspNetCore.DataProtection.KeyManagement.XmlKeyManager[0] ...
  info: Microsoft.AspNetCore.DataProtection.KeyManagement.XmlKeyManager[58] ...
  warn: Microsoft.AspNetCore.DataProtection.KeyManagement.XmlKeyManager[35] ...
  info: Microsoft.AspNetCore.DataProtection.Repositories.FileSystemXmlRepository[39] ...
  Hosting environment: Development
  Content root path: /Users/ac/_play/graphchangenotifications/msgraphapp
  Now listening on: https://localhost:5001
  Now listening on: http://localhost:5000
  Application started. Press Ctrl+C to shut down.
  ```

<span data-ttu-id="bfc3e-104">Beenden Sie die Ausführung der Anwendung, indem Sie <kbd>STRG +</kbd>+<kbd>C</kbd>drücken.</span><span class="sxs-lookup"><span data-stu-id="bfc3e-104">Stop the application running by pressing <kbd>CTRL</kbd>+<kbd>C</kbd>.</span></span>

<span data-ttu-id="bfc3e-105">Öffnen Sie die Anwendung in Visual Studio Code mit dem folgenden Befehl:</span><span class="sxs-lookup"><span data-stu-id="bfc3e-105">Open the application in Visual Studio Code using the following command:</span></span>

```shell
code .
```

<span data-ttu-id="bfc3e-106">Wenn in Visual Studio Code ein Dialogfeld angezeigt wird, in dem Sie gefragt werden, ob Sie dem Projekt erforderliche Objekte hinzufügen möchten, wählen Sie **Ja**aus.</span><span class="sxs-lookup"><span data-stu-id="bfc3e-106">If Visual Studio code displays a dialog box asking if you want to add required assets to the project, select **Yes**.</span></span>
