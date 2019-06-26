<!-- markdownlint-disable MD002 MD041 -->

In dieser Übung erstellen Sie eine neue Azure AD-Webanwendungs Registrierung mithilfe des Azure Active Directory Admin Center und erteilen dem Administrator die Zustimmung zu den erforderlichen Berechtigungs Bereichen.

1. Öffnen Sie einen Browser, und navigieren Sie zum [Azure Active Directory Adminhttps://aad.portal.azure.com)Center (](https://aad.portal.azure.com). Melden Sie sich mit einem **geschäftlichen oder Schulkonto**an.

1. Wählen Sie in der linken Navigationsleiste **Azure Active Directory** aus, und wählen Sie dann **App** -Registrierungen unter **Manage**aus.

    ![Screenshot der APP-Registrierungen](./images/aad-portal-home.png)

1. Wählen Sie **Neue Registrierung** aus. Auf der Seite " **Anwendung registrieren** "

    ![Screenshot der Seite "App-Registrierungen"](./images/aad-portal-newapp.png)

    Legen Sie die Werte wie folgt fest:

    - **Name**: GraphNotificationTutorial
    - **Unterstützte Kontotypen**: Konten in einem Organisations Verzeichnis und persönlichen Microsoft-Konten
    - Umleitungs- **URI**: Web#a0http://localhost

    ![Screenshot der Seite "Anwendung registrieren"](./images/aad-portal-newapp-01.png)

    Wählen Sie **registrieren**aus.

1. Kopieren Sie auf der Seite **GraphNotificationTutorial** den Wert der Anwendungs-ID **(Client)** und **Verzeichnis (** Mandanten-ID), speichern Sie ihn, benötigen Sie diese im nächsten Schritt.

    ![Screenshot der Anwendungs-ID der neuen App-Registrierung](./images/aad-portal-newapp-details.png)

1. Wählen Sie **#a0 Zertifikate verwalten #a1 Geheimnisse**aus. 

    Wählen Sie **neuer geheimer Client Schlüssel**aus.

    Geben Sie einen Wert in **Description** ein, und wählen Sie eine der Optionen für **Ablaufdatum** aus, und wählen Sie **Hinzufügen**aus.

    ![Screenshot des Dialogfelds zum Hinzufügen eines geheimen Client Schlüssels](./images/aad-portal-newapp-secret.png)

    ![Screenshot des Dialogfelds zum Hinzufügen eines geheimen Client Schlüssels](./images/aad-portal-newapp-secret-02.png)

1. Kopieren Sie den Wert des geheimen Clientschlüssels, bevor Sie diese Seite verlassen. Sie benötigen ihn im nächsten Schritt.

    > [!IMPORTANT]
    > Dieser geheime Clientschlüssel wird nicht noch einmal angezeigt, stellen Sie daher sicher, dass Sie ihn jetzt kopieren.

    ![Screenshot des neu hinzugefügten geheimen Client Schlüssels](./images/aad-portal-newapp-secret-03.png)

1. Wählen Sie **#a0 API-Berechtigungen verwalten**aus.

    Wählen Sie **Berechtigung hinzufügen** aus, und wählen Sie **Microsoft Graph**aus.

    ![Screenshot auswählen des Microsoft Graph-Diensts](./images/aad-portal-newapp-graphscope.png)

    Wählen Sie **Anwendungsberechtigung**aus, erweitern Sie die **Benutzer** Gruppe, und wählen Sie **Benutzer. ReadWrite. all** aus.

    Wählen Sie **Berechtigungen hinzufügen** aus, um Ihre Änderungen zu speichern.

    ![Screenshot auswählen von Microsoft Graph-Bereich](./images/aad-portal-newapp-graphscope-02.png)

    ![Screenshot des neu hinzugefügten geheimen Client Schlüssels](./images/aad-portal-newapp-graphscope-03.png)

Die Anwendung fordert eine Anwendungsberechtigung mit dem **Benutzer. ReadWrite. all** -Bereich an. Für diese Berechtigung ist eine administrative Zustimmung erforderlich.

Wählen Sie **Administrator Zustimmung für Contoso erteilen**aus, und wählen Sie **Ja** aus, um dieser Anwendung zuzustimmen, und gewähren Sie der Anwendung den Zugriff auf ihren Mandanten mithilfe der von Ihnen angegebenen Bereiche.

![Screenshot genehmigte Zustimmung des Administrators](./images/aad-portal-newapp-graphscope-04.png)
