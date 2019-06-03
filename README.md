# <a name="microsoft-graph-training-module---using-change-notifications-and-track-changes-with-microsoft-graph"></a><span data-ttu-id="0d79a-101">Microsoft Graph-Schulungsmodul – Verwenden von Änderungsbenachrichtigungen und Nachverfolgen von Änderungen mit Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="0d79a-101">Microsoft Graph Training Module - Using Change Notifications and Track Changes with Microsoft Graph</span></span>

<span data-ttu-id="0d79a-102">Dieses Modul enthält eine Einführung in das Arbeiten mit Änderungsbenachrichtigungen (webhooks) #a0 Nachverfolgen von Änderungen (Delta-Abfrage) im Microsoft Graph.</span><span class="sxs-lookup"><span data-stu-id="0d79a-102">This module will introduce you to working with change notifications (webhooks) & track changes (delta query) in the Microsoft Graph.</span></span>

## <a name="lab---change-notifications-and-track-changes-with-the-microsoft-graph"></a><span data-ttu-id="0d79a-103">Lab – Änderungsbenachrichtigungen und Nachverfolgen von Änderungen mit Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="0d79a-103">Lab - Change Notifications and Track Changes with the Microsoft Graph</span></span>

<span data-ttu-id="0d79a-104">In dieser Übungseinheit erstellen Sie eine .net-Kern Konsolenanwendung, die Änderungsbenachrichtigungen von Microsoft Graph erhält, wenn ein Benutzerkonto in Azure Active Directory (Azure AD) aktualisiert wird.</span><span class="sxs-lookup"><span data-stu-id="0d79a-104">In this lab you will create a .NET Core console application that receives change notifications from the Microsoft Graph when an update is made to a users account in Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="0d79a-105">Die Anwendung verwaltet das Änderungs Benachrichtigungsabonnement und verwendet Nachverfolgen von Änderungen in Microsoft Graph, um sicherzustellen, dass keine Änderungen verpasst werden.</span><span class="sxs-lookup"><span data-stu-id="0d79a-105">The application will managed the Change Notification subscription and use Track Changes in the Microsoft Graph to ensure no changes are missed.</span></span>

- [<span data-ttu-id="0d79a-106">Lab-Handbuch</span><span class="sxs-lookup"><span data-stu-id="0d79a-106">Lab Manual</span></span>](./Lab.md)

## <a name="demos"></a><span data-ttu-id="0d79a-107">Demos</span><span class="sxs-lookup"><span data-stu-id="0d79a-107">Demos</span></span>

- [<span data-ttu-id="0d79a-108">Erstellen einer .net Core-App</span><span class="sxs-lookup"><span data-stu-id="0d79a-108">Create a .NET Core app</span></span>](./demos/01-create-application)
- [<span data-ttu-id="0d79a-109">Abonnement Lebenszyklus hinzufügen</span><span class="sxs-lookup"><span data-stu-id="0d79a-109">Add Subscription Lifecycle</span></span>](./demos/02-subscription-management)
- [<span data-ttu-id="0d79a-110">Hinzufügen von Änderungen nachverfolgen</span><span class="sxs-lookup"><span data-stu-id="0d79a-110">Add Track Changes</span></span>](./demos/03-track-changes)

## <a name="watch-the-module"></a><span data-ttu-id="0d79a-111">Modul ansehen</span><span class="sxs-lookup"><span data-stu-id="0d79a-111">Watch the module</span></span>

<span data-ttu-id="0d79a-112">Dieses Modul wurde aufgezeichnet und steht im YouTube-Kanal für Office-Entwicklung zur Verfügung: [Änderungsbenachrichtigungen und Nachverfolgen von Änderungen mit Microsoft Graph](https://youtu.be/MvJ15BHTdHA)</span><span class="sxs-lookup"><span data-stu-id="0d79a-112">This module has been recorded and is available in the Office Development YouTube channel: [Change Notifications and Track Changes with the Microsoft Graph](https://youtu.be/MvJ15BHTdHA)</span></span>

## <a name="contributors"></a><span data-ttu-id="0d79a-113">Mitwirkende</span><span class="sxs-lookup"><span data-stu-id="0d79a-113">Contributors</span></span>

| <span data-ttu-id="0d79a-114">Rollen</span><span class="sxs-lookup"><span data-stu-id="0d79a-114">Roles</span></span>                | <span data-ttu-id="0d79a-115">Autor (en)</span><span class="sxs-lookup"><span data-stu-id="0d79a-115">Author(s)</span></span>                                               |
| -------------------- | ------------------------------------------------------- |
| <span data-ttu-id="0d79a-116">Lab-Handbücher/Folien</span><span class="sxs-lookup"><span data-stu-id="0d79a-116">Lab Manuals / Slides</span></span> | <span data-ttu-id="0d79a-117">Andrew Connell (Microsoft MVP, Voitanos) @andrewconnell</span><span class="sxs-lookup"><span data-stu-id="0d79a-117">Andrew Connell (Microsoft MVP, Voitanos) @andrewconnell</span></span> |
| <span data-ttu-id="0d79a-118">Sponsor/Support</span><span class="sxs-lookup"><span data-stu-id="0d79a-118">Sponsor / Support</span></span>    | <span data-ttu-id="0d79a-119">Jeremy den (Microsoft) @jthake</span><span class="sxs-lookup"><span data-stu-id="0d79a-119">Jeremy Thake (Microsoft) @jthake</span></span>                        |

## <a name="version-history"></a><span data-ttu-id="0d79a-120">Versionsverlauf</span><span class="sxs-lookup"><span data-stu-id="0d79a-120">Version history</span></span>

| <span data-ttu-id="0d79a-121">Version</span><span class="sxs-lookup"><span data-stu-id="0d79a-121">Version</span></span> | <span data-ttu-id="0d79a-122">Datum</span><span class="sxs-lookup"><span data-stu-id="0d79a-122">Date</span></span>           | <span data-ttu-id="0d79a-123">Kommentare</span><span class="sxs-lookup"><span data-stu-id="0d79a-123">Comments</span></span>             |
| ------- | -------------- | -------------------- |
| <span data-ttu-id="0d79a-124">1.1</span><span class="sxs-lookup"><span data-stu-id="0d79a-124">1.1</span></span>     | <span data-ttu-id="0d79a-125">9. April 2019</span><span class="sxs-lookup"><span data-stu-id="0d79a-125">April 9, 2019</span></span> | <span data-ttu-id="0d79a-126">Screencast-Link hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="0d79a-126">Added screencast link</span></span> |
| <span data-ttu-id="0d79a-127">1.0</span><span class="sxs-lookup"><span data-stu-id="0d79a-127">1.0</span></span>     | <span data-ttu-id="0d79a-128">14. März 2019</span><span class="sxs-lookup"><span data-stu-id="0d79a-128">March 14, 2019</span></span> | <span data-ttu-id="0d79a-129">Neues Modul übermittelt</span><span class="sxs-lookup"><span data-stu-id="0d79a-129">New module submitted</span></span> |

## <a name="disclaimer"></a><span data-ttu-id="0d79a-130">Verzichtserklärung</span><span class="sxs-lookup"><span data-stu-id="0d79a-130">Disclaimer</span></span>

<span data-ttu-id="0d79a-131">**Dieser Code wird ohne __ jegliche ausdrückliche oder implizite Gewährleistung bereitgestellt, einschließlich impliziter Garantien für die Eignung für einen bestimmten Zweck, die Marktgängigkeit oder die Nichtverletzung.**</span><span class="sxs-lookup"><span data-stu-id="0d79a-131">**THIS CODE IS PROVIDED _AS IS_ WITHOUT WARRANTY OF ANY KIND, EITHER EXPRESS OR IMPLIED, INCLUDING ANY IMPLIED WARRANTIES OF FITNESS FOR A PARTICULAR PURPOSE, MERCHANTABILITY, OR NON-INFRINGEMENT.**</span></span>

<img src="https://telemetry.sharepointpnp.com/msgraph-training-changenotifications" />
