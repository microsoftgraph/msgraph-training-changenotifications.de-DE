<!-- markdownlint-disable MD002 MD041 -->

Öffnen Sie die Eingabeaufforderung, navigieren Sie zu einem Verzeichnis, in dem Sie über Rechte zum Erstellen Ihres Projekts verfügen, und führen Sie den folgenden Befehl aus, um eine neue .net Core-WebApi-APP zu erstellen:

```shell
dotnet new webapi -o msgraphapp
```

Führen Sie nach dem Erstellen der Anwendung die folgenden Befehle aus, um sicherzustellen, dass das neue Projekt ordnungsgemäß ausgeführt wird.

  ```shell
  cd msgraphapp
  dotnet add package Microsoft.Identity.Client
  dotnet add package Microsoft.Graph
  dotnet run
  ```

  Die Anwendung wird Folgendes starten und ausgeben:

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

Beenden Sie die Ausführung der Anwendung, indem Sie <kbd>STRG +</kbd>+<kbd>C</kbd>drücken.

Öffnen Sie die Anwendung in Visual Studio Code mit dem folgenden Befehl:

```shell
code .
```

Wenn in Visual Studio Code ein Dialogfeld angezeigt wird, in dem Sie gefragt werden, ob Sie dem Projekt erforderliche Objekte hinzufügen möchten, wählen Sie **Ja**aus.
