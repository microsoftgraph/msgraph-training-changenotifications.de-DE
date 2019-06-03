<!-- markdownlint-disable MD002 MD041 -->

Öffnen Sie die Eingabeaufforderung, navigieren Sie zu einem Verzeichnis, in dem Sie Berechtigungen zum Erstellen von Dateien haben, und führen Sie die folgenden Befehle aus, um eine neue .net Core-WebApi-APP zu erstellen.

```shell
dotnet new webapi -o msgraphapp
```

Nachdem der Befehl abgeschlossen ist, führen Sie die folgenden Befehle aus, um sicherzustellen, dass Ihr neues Projekt ordnungsgemäß ausgeführt wird.

```shell
cd msgraphapp
dotnet add package Microsoft.Identity.Client
dotnet add package Microsoft.Graph
dotnet run
```

Die Anwendung wird gestartet und ausgegeben:

```shell
Now listening on: http://localhost:5000
```

Wenn diese Ausgabe nicht angezeigt wird oder Fehlermeldungen angezeigt werden, liegt wahrscheinlich ein Problem mit dem [.net Core 2,2 SDK](https://dotnet.microsoft.com/download) vor, das auf dem Entwicklungscomputer installiert ist und vor dem Fortfahren behoben werden muss.

Beenden Sie die Ausführung der Anwendung, indem Sie <kbd>STRG +</kbd>+<kbd>C</kbd>drücken.

Öffnen Sie die Anwendung in Visual Studio Code mit dem folgenden Befehl:

```shell
code .
```

Wenn Sie in einem Dialogfeld gefragt werden, ob Sie dem Projekt erforderliche Objekte hinzufügen möchten, wählen Sie **Ja**aus.
