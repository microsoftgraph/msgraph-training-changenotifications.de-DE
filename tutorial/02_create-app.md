<!-- markdownlint-disable MD002 MD041 -->

<span data-ttu-id="b9af1-101">In dieser Übung erstellen Sie eine neue Azure AD-Webanwendungs Registrierung mithilfe des Azure Active Directory Admin Center und erteilen dem Administrator die Zustimmung zu den erforderlichen Berechtigungs Bereichen.</span><span class="sxs-lookup"><span data-stu-id="b9af1-101">In this exercise, you will create a new Azure AD web application registration using the Azure Active Directory admin center and grant administrator consent to the required permission scopes.</span></span>

1. <span data-ttu-id="b9af1-102">Öffnen Sie einen Browser, und navigieren Sie zum [Azure Active Directory Admin Center](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="b9af1-102">Open a browser and navigate to the [Azure Active Directory admin center](https://portal.azure.com).</span></span> <span data-ttu-id="b9af1-103">Melden Sie sich mit einem **geschäftlichen oder Schulkonto**an.</span><span class="sxs-lookup"><span data-stu-id="b9af1-103">Login using a **Work or School Account**.</span></span>

1. <span data-ttu-id="b9af1-104">Wählen Sie in der linken Navigationsleiste **Azure Active Directory** aus, und wählen Sie dann **App-Registrierungen (Vorschau)** unter **Verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="b9af1-104">Select **Azure Active Directory** in the left-hand navigation, then select **App registrations (Preview)** under **Manage**.</span></span>

    ![<span data-ttu-id="b9af1-105">Ein Screenshot der APP-Registrierungen</span><span class="sxs-lookup"><span data-stu-id="b9af1-105">A screenshot of the App registrations</span></span> ](./images/01.png)

1. <span data-ttu-id="b9af1-106">Wählen Sie **Neue Registrierung** aus.</span><span class="sxs-lookup"><span data-stu-id="b9af1-106">Select **New registration**.</span></span> <span data-ttu-id="b9af1-107">Legen Sie auf der Seite **Anwendung registrieren** die Werte wie folgt fest.</span><span class="sxs-lookup"><span data-stu-id="b9af1-107">On the **Register an application** page, set the values as follows.</span></span>

    - <span data-ttu-id="b9af1-108">Legen Sie **Name** auf `GraphNotificationTutorial` fest.</span><span class="sxs-lookup"><span data-stu-id="b9af1-108">Set **Name** to `GraphNotificationTutorial`.</span></span>
    - <span data-ttu-id="b9af1-109">Legen Sie **Unterstützte Kontotypen** auf **Konten in allen Organisationsverzeichnissen und persönliche Microsoft-Konten** fest.</span><span class="sxs-lookup"><span data-stu-id="b9af1-109">Set **Supported account types** to **Accounts in any organizational directory and personal Microsoft accounts**.</span></span>
    - <span data-ttu-id="b9af1-110">Legen Sie unter **Umleitungs-URI** die erste Dropdownoption auf `Web` fest, und legen Sie den Wert auf `http://localhost` fest.</span><span class="sxs-lookup"><span data-stu-id="b9af1-110">Under **Redirect URI**, set the first drop-down to `Web` and set the value to `http://localhost`.</span></span>

    ![Screenshot der Seite "Anwendung registrieren"](./images/02.png)

1. <span data-ttu-id="b9af1-112">Wählen Sie **registrieren**aus.</span><span class="sxs-lookup"><span data-stu-id="b9af1-112">Select **Register**.</span></span> <span data-ttu-id="b9af1-113">Kopieren Sie auf der Seite **GraphNotificationTutorial** den Wert der Anwendungs-ID **(Client)** und **Verzeichnis (** Mandanten-ID), speichern Sie ihn, benötigen Sie diese im nächsten Schritt.</span><span class="sxs-lookup"><span data-stu-id="b9af1-113">On the **GraphNotificationTutorial** page, copy the value of the **Application (client) ID** and **Directory (tenant) ID** save it, you will need them in the next step.</span></span>

    ![Ein Screenshot der Anwendungs-ID der neuen App-Registrierung](./images/03.png)

1. <span data-ttu-id="b9af1-115">Wählen Sie unter **Verwalten** die Option **Zertifikate und Geheime Clientschlüssel** aus.</span><span class="sxs-lookup"><span data-stu-id="b9af1-115">Select **Certificates & secrets** under **Manage**.</span></span> <span data-ttu-id="b9af1-116">Wählen Sie **neuer geheimer Client Schlüssel**aus.</span><span class="sxs-lookup"><span data-stu-id="b9af1-116">Select **New client secret**.</span></span> <span data-ttu-id="b9af1-117">Geben Sie einen Wert in **Description** ein, und wählen Sie eine der Optionen für **Ablaufdatum** aus, und wählen Sie **Hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="b9af1-117">Enter a value in **Description** and select one of the options for **Expires** and select **Add**.</span></span>

    ![Screenshot des Dialogfelds zum Hinzufügen eines geheimen Client Schlüssels](./images/04.png)

1. <span data-ttu-id="b9af1-119">Kopieren Sie den Wert des geheimen Clientschlüssels, bevor Sie diese Seite verlassen.</span><span class="sxs-lookup"><span data-stu-id="b9af1-119">Copy the client secret value before you leave this page.</span></span> <span data-ttu-id="b9af1-120">Sie benötigen ihn im nächsten Schritt.</span><span class="sxs-lookup"><span data-stu-id="b9af1-120">You will need it in the next step.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="b9af1-121">Dieser geheime Clientschlüssel wird nicht noch einmal angezeigt, stellen Sie daher sicher, dass Sie ihn jetzt kopieren.</span><span class="sxs-lookup"><span data-stu-id="b9af1-121">This client secret is never shown again, so make sure you copy it now.</span></span>

    ![Screenshot des neu hinzugefügten geheimen Client Schlüssels](./images/05.png)

1. <span data-ttu-id="b9af1-123">Wählen Sie unter **Manage**die **API-Berechtigungen** aus.</span><span class="sxs-lookup"><span data-stu-id="b9af1-123">Select **API Permissions** under **Manage**.</span></span> <span data-ttu-id="b9af1-124">**Fügen Sie eine Berechtigung hinzu** , und wählen Sie **Microsoft Graph**aus.</span><span class="sxs-lookup"><span data-stu-id="b9af1-124">**Add a permission** and select **Microsoft Graph**.</span></span> <span data-ttu-id="b9af1-125">Wählen Sie **Anwendungsberechtigung** aus, und erweitern Sie **Benutzer** , und wählen Sie den Bereich **Benutzer. ReadWrite. all** aus.</span><span class="sxs-lookup"><span data-stu-id="b9af1-125">Select **Application Permission** and expand **User** and select the **User.ReadWrite.All** scope.</span></span> <span data-ttu-id="b9af1-126">Wählen Sie **Berechtigungen hinzufügen** aus, um Ihre Änderungen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="b9af1-126">Select **Add permissions** to save your changes.</span></span>

    ![Screenshot des neu hinzugefügten geheimen Client Schlüssels](./images/06.png)

<span data-ttu-id="b9af1-128">Die Anwendung fordert eine Anwendungsberechtigung mit dem **Benutzer. ReadWrite. all** -Bereich an.</span><span class="sxs-lookup"><span data-stu-id="b9af1-128">The application requests an application permission with the **User.ReadWrite.All** scope.</span></span> <span data-ttu-id="b9af1-129">Für diese Berechtigung ist eine administrative Zustimmung erforderlich.</span><span class="sxs-lookup"><span data-stu-id="b9af1-129">This permission requires administrative consent.</span></span>

<span data-ttu-id="b9af1-130">Wählen Sie **Administrator Zustimmung für Contoso erteilen** aus, und klicken Sie dann auf **Ja** , um dieser Anwendung zuzustimmen, und gewähren Sie der Anwendung den Zugriff auf ihren Mandanten mithilfe der von Ihnen angegebenen Bereiche.</span><span class="sxs-lookup"><span data-stu-id="b9af1-130">Select **Grant admin consent for Contoso** and then select **Yes** to consent this application and grant the application access to your tenant using the scopes you specified.</span></span>

![Screenshot der Anmeldung](./images/07.png)
