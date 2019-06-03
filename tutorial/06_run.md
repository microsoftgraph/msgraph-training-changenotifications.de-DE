<!-- markdownlint-disable MD002 MD041 -->

Wählen Sie **Debug #a0 Debuggen starten** aus, um die Anwendung auszuführen. Nach dem Erstellen der Anwendung wird ein Browserfenster geöffnet, das auf einer 404-Seite angezeigt wird. Dies ist in Ordnung, da es sich bei unserer Anwendung um eine API und nicht um eine Webseite handelt.

Um Änderungsbenachrichtigungen für Benutzer zu abonnieren, navigieren Sie zur folgenden `http://localhost:5000/api/notifications`URL. Bei erfolgreicher Ausführung wird eine Ausgabe mit einer Abonnement-ID wie die folgende angezeigt:

```shell
Subscribed. Id: e2dbfbe1-160b-42b0-9b9f-8ab79bf8dfed
```

Ihre Anwendung abonniert jetzt Benachrichtigungen von Microsoft Graph, wenn ein Update für alle Benutzer im Office 365 Mandanten vorgenommen wird.

Öffnen Sie einen Browser, und besuchen Sie das [Microsoft 365 Admin Center](https://admin.microsoft.com/AdminPortal). Melden Sie sich mit einem Administratorkonto an. Wählen Sie **Benutzer #a0 aktive Benutzer**aus. Wählen Sie einen aktiven Benutzer aus, und wählen Sie **Bearbeiten** als **Kontaktinformationen**aus. Aktualisieren Sie den Wert für **Mobiltelefone** mit einer neuen Nummer, und wählen Sie **Speichern**aus.

![Screenshot der Benutzer Details](./images/03.png)

In der **Debug-Konsole** von Visual Studio wird eine Benachrichtigung empfangen. Manchmal kann es einige Minuten dauern, bis Sie eintreffen. Ein Beispiel für die Ausgabe ist unten:

```shell
Received notification: 'Users/7a7fded6-0269-42c2-a0be-512d58da4463', 7a7fded6-0269-42c2-a0be-512d58da4463
```

Dadurch wird angegeben, dass die Anwendung die Benachrichtigung vom Microsoft Graph erfolgreich für den in der Ausgabe angegebenen Benutzer erhalten hat. Anschließend können Sie diese Informationen verwenden, um das Diagramm für die Benutzer vollständigen Details abzufragen, wenn Sie Ihre Details in Ihrer Anwendung synchronisieren möchten.