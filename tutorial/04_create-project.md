<!-- markdownlint-disable MD002 MD041 -->

<span data-ttu-id="e1b40-101">Öffnen Sie die Eingabeaufforderung, navigieren Sie zu einem Verzeichnis, in dem Sie Berechtigungen zum Erstellen von Dateien haben, und führen Sie die folgenden Befehle aus, um eine neue .net Core-WebApi-APP zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="e1b40-101">Open your command prompt, navigate to a directory where you have rights to create files, and run the following commands to create a new .NET Core WebApi app.</span></span>

```shell
dotnet new webapi -o msgraphapp
```

<span data-ttu-id="e1b40-102">Nachdem der Befehl abgeschlossen ist, führen Sie die folgenden Befehle aus, um sicherzustellen, dass Ihr neues Projekt ordnungsgemäß ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="e1b40-102">Once the command finishes, run the following commands to ensure your new project runs correctly.</span></span>

```shell
cd msgraphapp
dotnet add package Microsoft.Identity.Client
dotnet add package Microsoft.Graph
dotnet run
```

<span data-ttu-id="e1b40-103">Die Anwendung wird gestartet und ausgegeben:</span><span class="sxs-lookup"><span data-stu-id="e1b40-103">The application will start and output:</span></span>

```shell
Now listening on: http://localhost:5000
```

<span data-ttu-id="e1b40-104">Wenn diese Ausgabe nicht angezeigt wird oder Fehlermeldungen angezeigt werden, liegt wahrscheinlich ein Problem mit dem [.net Core 2,2 SDK](https://dotnet.microsoft.com/download) vor, das auf dem Entwicklungscomputer installiert ist und vor dem Fortfahren behoben werden muss.</span><span class="sxs-lookup"><span data-stu-id="e1b40-104">If you don't see this output, or you see error messages, there is likely a problem with the [.NET Core 2.2 SDK](https://dotnet.microsoft.com/download) installed on your development machine that needs to be fixed before continuing.</span></span>

<span data-ttu-id="e1b40-105">Beenden Sie die Ausführung der Anwendung, indem Sie <kbd>STRG +</kbd>+<kbd>C</kbd>drücken.</span><span class="sxs-lookup"><span data-stu-id="e1b40-105">Stop the application running by pressing <kbd>CTRL</kbd>+<kbd>C</kbd>.</span></span>

<span data-ttu-id="e1b40-106">Öffnen Sie die Anwendung in Visual Studio Code mit dem folgenden Befehl:</span><span class="sxs-lookup"><span data-stu-id="e1b40-106">Open the application in Visual Studio Code using the following command:</span></span>

```shell
code .
```

<span data-ttu-id="e1b40-107">Wenn Sie in einem Dialogfeld gefragt werden, ob Sie dem Projekt erforderliche Objekte hinzufügen möchten, wählen Sie **Ja**aus.</span><span class="sxs-lookup"><span data-stu-id="e1b40-107">When a dialog box asks if you want to add required assets to the project, select **Yes**.</span></span>
