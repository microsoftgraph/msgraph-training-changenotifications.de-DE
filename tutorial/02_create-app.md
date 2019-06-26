<!-- markdownlint-disable MD002 MD041 -->

<span data-ttu-id="9d3e5-101">In dieser Übung erstellen Sie eine neue Azure AD-Webanwendungs Registrierung mithilfe des Azure Active Directory Admin Center und erteilen dem Administrator die Zustimmung zu den erforderlichen Berechtigungs Bereichen.</span><span class="sxs-lookup"><span data-stu-id="9d3e5-101">In this exercise, you will create a new Azure AD web application registration using the Azure Active Directory admin center and grant administrator consent to the required permission scopes.</span></span>

1. <span data-ttu-id="9d3e5-102">Öffnen Sie einen Browser, und navigieren Sie zum [Azure Active Directory Adminhttps://aad.portal.azure.com)Center (](https://aad.portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="9d3e5-102">Open a browser and navigate to the [Azure Active Directory admin center (https://aad.portal.azure.com)](https://aad.portal.azure.com).</span></span> <span data-ttu-id="9d3e5-103">Melden Sie sich mit einem **geschäftlichen oder Schulkonto**an.</span><span class="sxs-lookup"><span data-stu-id="9d3e5-103">Login using a **Work or School Account**.</span></span>

1. <span data-ttu-id="9d3e5-104">Wählen Sie in der linken Navigationsleiste **Azure Active Directory** aus, und wählen Sie dann **App** -Registrierungen unter **Manage**aus.</span><span class="sxs-lookup"><span data-stu-id="9d3e5-104">Select **Azure Active Directory** in the left-hand navigation, then select **App registrations** under **Manage**.</span></span>

    ![Screenshot der APP-Registrierungen](./images/aad-portal-home.png)

1. <span data-ttu-id="9d3e5-106">Wählen Sie **Neue Registrierung** aus.</span><span class="sxs-lookup"><span data-stu-id="9d3e5-106">Select **New registration**.</span></span> <span data-ttu-id="9d3e5-107">Auf der Seite " **Anwendung registrieren** "</span><span class="sxs-lookup"><span data-stu-id="9d3e5-107">On the **Register an application** page</span></span>

    ![Screenshot der Seite "App-Registrierungen"](./images/aad-portal-newapp.png)

    <span data-ttu-id="9d3e5-109">Legen Sie die Werte wie folgt fest:</span><span class="sxs-lookup"><span data-stu-id="9d3e5-109">Set the values as follows:</span></span>

    - <span data-ttu-id="9d3e5-110">**Name**: GraphNotificationTutorial</span><span class="sxs-lookup"><span data-stu-id="9d3e5-110">**Name**: GraphNotificationTutorial</span></span>
    - <span data-ttu-id="9d3e5-111">**Unterstützte Kontotypen**: Konten in einem Organisations Verzeichnis und persönlichen Microsoft-Konten</span><span class="sxs-lookup"><span data-stu-id="9d3e5-111">**Supported account types**: Accounts in any organizational directory and personal Microsoft accounts</span></span>
    - <span data-ttu-id="9d3e5-112">Umleitungs- **URI**: Web#a0http://localhost</span><span class="sxs-lookup"><span data-stu-id="9d3e5-112">**Redirect URI**: Web > http://localhost</span></span>

    ![Screenshot der Seite "Anwendung registrieren"](./images/aad-portal-newapp-01.png)

    <span data-ttu-id="9d3e5-114">Wählen Sie **registrieren**aus.</span><span class="sxs-lookup"><span data-stu-id="9d3e5-114">Select **Register**.</span></span>

1. <span data-ttu-id="9d3e5-115">Kopieren Sie auf der Seite **GraphNotificationTutorial** den Wert der Anwendungs-ID **(Client)** und **Verzeichnis (** Mandanten-ID), speichern Sie ihn, benötigen Sie diese im nächsten Schritt.</span><span class="sxs-lookup"><span data-stu-id="9d3e5-115">On the **GraphNotificationTutorial** page, copy the value of the **Application (client) ID** and **Directory (tenant) ID** save it, you will need them in the next step.</span></span>

    ![Screenshot der Anwendungs-ID der neuen App-Registrierung](./images/aad-portal-newapp-details.png)

1. <span data-ttu-id="9d3e5-117">Wählen Sie **#a0 Zertifikate verwalten #a1 Geheimnisse**aus.</span><span class="sxs-lookup"><span data-stu-id="9d3e5-117">Select **Manage > Certificates & secrets**.</span></span> 

    <span data-ttu-id="9d3e5-118">Wählen Sie **neuer geheimer Client Schlüssel**aus.</span><span class="sxs-lookup"><span data-stu-id="9d3e5-118">Select **New client secret**.</span></span>

    <span data-ttu-id="9d3e5-119">Geben Sie einen Wert in **Description** ein, und wählen Sie eine der Optionen für **Ablaufdatum** aus, und wählen Sie **Hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="9d3e5-119">Enter a value in **Description** and select one of the options for **Expires** and select **Add**.</span></span>

    ![Screenshot des Dialogfelds zum Hinzufügen eines geheimen Client Schlüssels](./images/aad-portal-newapp-secret.png)

    ![Screenshot des Dialogfelds zum Hinzufügen eines geheimen Client Schlüssels](./images/aad-portal-newapp-secret-02.png)

1. <span data-ttu-id="9d3e5-122">Kopieren Sie den Wert des geheimen Clientschlüssels, bevor Sie diese Seite verlassen.</span><span class="sxs-lookup"><span data-stu-id="9d3e5-122">Copy the client secret value before you leave this page.</span></span> <span data-ttu-id="9d3e5-123">Sie benötigen ihn im nächsten Schritt.</span><span class="sxs-lookup"><span data-stu-id="9d3e5-123">You will need it in the next step.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="9d3e5-124">Dieser geheime Clientschlüssel wird nicht noch einmal angezeigt, stellen Sie daher sicher, dass Sie ihn jetzt kopieren.</span><span class="sxs-lookup"><span data-stu-id="9d3e5-124">This client secret is never shown again, so make sure you copy it now.</span></span>

    ![Screenshot des neu hinzugefügten geheimen Client Schlüssels](./images/aad-portal-newapp-secret-03.png)

1. <span data-ttu-id="9d3e5-126">Wählen Sie **#a0 API-Berechtigungen verwalten**aus.</span><span class="sxs-lookup"><span data-stu-id="9d3e5-126">Select **Manage > API Permissions**.</span></span>

    <span data-ttu-id="9d3e5-127">Wählen Sie **Berechtigung hinzufügen** aus, und wählen Sie **Microsoft Graph**aus.</span><span class="sxs-lookup"><span data-stu-id="9d3e5-127">Select **Add a permission** and select **Microsoft Graph**.</span></span>

    ![Screenshot auswählen des Microsoft Graph-Diensts](./images/aad-portal-newapp-graphscope.png)

    <span data-ttu-id="9d3e5-129">Wählen Sie **Anwendungsberechtigung**aus, erweitern Sie die **Benutzer** Gruppe, und wählen Sie **Benutzer. ReadWrite. all** aus.</span><span class="sxs-lookup"><span data-stu-id="9d3e5-129">Select **Application Permission**, expand the **User** group and select **User.ReadWrite.All** scope.</span></span>

    <span data-ttu-id="9d3e5-130">Wählen Sie **Berechtigungen hinzufügen** aus, um Ihre Änderungen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="9d3e5-130">Select **Add permissions** to save your changes.</span></span>

    ![Screenshot auswählen von Microsoft Graph-Bereich](./images/aad-portal-newapp-graphscope-02.png)

    ![Screenshot des neu hinzugefügten geheimen Client Schlüssels](./images/aad-portal-newapp-graphscope-03.png)

<span data-ttu-id="9d3e5-133">Die Anwendung fordert eine Anwendungsberechtigung mit dem **Benutzer. ReadWrite. all** -Bereich an.</span><span class="sxs-lookup"><span data-stu-id="9d3e5-133">The application requests an application permission with the **User.ReadWrite.All** scope.</span></span> <span data-ttu-id="9d3e5-134">Für diese Berechtigung ist eine administrative Zustimmung erforderlich.</span><span class="sxs-lookup"><span data-stu-id="9d3e5-134">This permission requires administrative consent.</span></span>

<span data-ttu-id="9d3e5-135">Wählen Sie **Administrator Zustimmung für Contoso erteilen**aus, und wählen Sie **Ja** aus, um dieser Anwendung zuzustimmen, und gewähren Sie der Anwendung den Zugriff auf ihren Mandanten mithilfe der von Ihnen angegebenen Bereiche.</span><span class="sxs-lookup"><span data-stu-id="9d3e5-135">Select **Grant admin consent for Contoso**, then select **Yes** to consent this application and grant the application access to your tenant using the scopes you specified.</span></span>

![Screenshot genehmigte Zustimmung des Administrators](./images/aad-portal-newapp-graphscope-04.png)
