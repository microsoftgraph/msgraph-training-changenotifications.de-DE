<!-- markdownlint-disable MD002 MD041 -->

In dieser Übung erstellen Sie eine neue Azure AD-Webanwendungs Registrierung mithilfe des Azure Active Directory Admin Center und erteilen dem Administrator die Zustimmung zu den erforderlichen Berechtigungs Bereichen.

1. Öffnen Sie einen Browser, und navigieren Sie zum [Azure Active Directory Admin Center](https://portal.azure.com). Melden Sie sich mit einem **geschäftlichen oder Schulkonto**an.

1. Wählen Sie in der linken Navigationsleiste **Azure Active Directory** aus, und wählen Sie dann **App-Registrierungen (Vorschau)** unter **Verwalten** aus.

    ![Ein Screenshot der APP-Registrierungen ](./images/01.png)

1. Wählen Sie **Neue Registrierung** aus. Legen Sie auf der Seite **Anwendung registrieren** die Werte wie folgt fest.

    - Legen Sie **Name** auf `GraphNotificationTutorial` fest.
    - Legen Sie **Unterstützte Kontotypen** auf **Konten in allen Organisationsverzeichnissen und persönliche Microsoft-Konten** fest.
    - Legen Sie unter **Umleitungs-URI** die erste Dropdownoption auf `Web` fest, und legen Sie den Wert auf `http://localhost` fest.

    ![Screenshot der Seite "Anwendung registrieren"](./images/02.png)

1. Wählen Sie **registrieren**aus. Kopieren Sie auf der Seite **GraphNotificationTutorial** den Wert der Anwendungs-ID **(Client)** und **Verzeichnis (** Mandanten-ID), speichern Sie ihn, benötigen Sie diese im nächsten Schritt.

    ![Ein Screenshot der Anwendungs-ID der neuen App-Registrierung](./images/03.png)

1. Wählen Sie unter **Verwalten** die Option **Zertifikate und Geheime Clientschlüssel** aus. Wählen Sie **neuer geheimer Client Schlüssel**aus. Geben Sie einen Wert in **Description** ein, und wählen Sie eine der Optionen für **Ablaufdatum** aus, und wählen Sie **Hinzufügen**aus.

    ![Screenshot des Dialogfelds zum Hinzufügen eines geheimen Client Schlüssels](./images/04.png)

1. Kopieren Sie den Wert des geheimen Clientschlüssels, bevor Sie diese Seite verlassen. Sie benötigen ihn im nächsten Schritt.

    > [!IMPORTANT]
    > Dieser geheime Clientschlüssel wird nicht noch einmal angezeigt, stellen Sie daher sicher, dass Sie ihn jetzt kopieren.

    ![Screenshot des neu hinzugefügten geheimen Client Schlüssels](./images/05.png)

1. Wählen Sie unter **Manage**die **API-Berechtigungen** aus. **Fügen Sie eine Berechtigung hinzu** , und wählen Sie **Microsoft Graph**aus. Wählen Sie **Anwendungsberechtigung** aus, und erweitern Sie **Benutzer** , und wählen Sie den Bereich **Benutzer. ReadWrite. all** aus. Wählen Sie **Berechtigungen hinzufügen** aus, um Ihre Änderungen zu speichern.

    ![Screenshot des neu hinzugefügten geheimen Client Schlüssels](./images/06.png)

Die Anwendung fordert eine Anwendungsberechtigung mit dem **Benutzer. ReadWrite. all** -Bereich an. Für diese Berechtigung ist eine administrative Zustimmung erforderlich.

Wählen Sie **Administrator Zustimmung für Contoso erteilen** aus, und klicken Sie dann auf **Ja** , um dieser Anwendung zuzustimmen, und gewähren Sie der Anwendung den Zugriff auf ihren Mandanten mithilfe der von Ihnen angegebenen Bereiche.

![Screenshot der Anmeldung](./images/07.png)
