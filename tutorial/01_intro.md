<!-- markdownlint-disable MD002 MD041 -->

<span data-ttu-id="c7690-101">In diesem Lernprogramm erfahren Sie, wie Sie eine .net-Kern-app erstellen, die die Microsoft Graph-API zum Empfangen von Benachrichtigungen (webhooks) verwendet, wenn sich ein Benutzerkonto in Azure Active Directory (Azure AD) ändert und Abfragen mithilfe der Delta-Abfrage-API ausführt, um alle Änderungen an Benutzer zu empfangen. Konten seit der letzten Abfrage vorgenommen wurden.</span><span class="sxs-lookup"><span data-stu-id="c7690-101">This tutorial teaches you how to build a .NET Core app that uses the Microsoft Graph API to receive notifications (webhooks) when a user account changes in Azure Active Directory (Azure AD) and perform queries using the delta query API to receive all changes to user accounts since the last query was made.</span></span>

> [!TIP]
> <span data-ttu-id="c7690-102">Wenn Sie das fertige Lernprogramm einfach herunterladen möchten, können Sie das GitHub- [Repository](https://github.com/microsoftgraph/msgraph-training-changenotifications)herunterladen oder Klonen.</span><span class="sxs-lookup"><span data-stu-id="c7690-102">If you prefer to just download the completed tutorial, you can download or clone the [GitHub repository](https://github.com/microsoftgraph/msgraph-training-changenotifications).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="c7690-103">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="c7690-103">Prerequisites</span></span>

<span data-ttu-id="c7690-104">Bevor Sie mit diesem Lernprogramm beginnen, sollten Sie [.net Core 2,2 SDK](https://dotnet.microsoft.com/download) und [Visual Studio Code](https://code.visualstudio.com/) auf Ihrem Entwicklungscomputer installiert haben.</span><span class="sxs-lookup"><span data-stu-id="c7690-104">Before you start this tutorial, you should have [.NET Core 2.2 SDK](https://dotnet.microsoft.com/download) and [Visual Studio Code](https://code.visualstudio.com/) installed on your development machine.</span></span>

> [!NOTE]
> <span data-ttu-id="c7690-105">Dieses Lernprogramm wurde mit .net Core Version 2,2 geschrieben.</span><span class="sxs-lookup"><span data-stu-id="c7690-105">This tutorial was written with .NET Core version 2.2.</span></span> <span data-ttu-id="c7690-106">Die Schritte in diesem Leitfaden funktionieren möglicherweise mit anderen Versionen, jedoch nicht getestet.</span><span class="sxs-lookup"><span data-stu-id="c7690-106">The steps in this guide may work with other versions, but that has not been tested.</span></span>

## <a name="watch-the-tutorial"></a><span data-ttu-id="c7690-107">Das Lernprogramm ansehen</span><span class="sxs-lookup"><span data-stu-id="c7690-107">Watch the tutorial</span></span>

<span data-ttu-id="c7690-108">Dieses Modul wurde aufgezeichnet und steht im YouTube-Kanal für die Office-Entwicklung zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="c7690-108">This module has been recorded and is available in the Office Development YouTube channel.</span></span>

<!-- markdownlint-disable MD033 MD034 -->
<br/>

> [!VIDEO https://www.youtube-nocookie.com/embed/fThiCZmIcMQ]
<!-- markdownlint-enable MD033 MD034 -->

## <a name="feedback"></a><span data-ttu-id="c7690-109">Feedback</span><span class="sxs-lookup"><span data-stu-id="c7690-109">Feedback</span></span>

<span data-ttu-id="c7690-110">Geben Sie Feedback zu diesem Lernprogramm im [GitHub-Repository](https://github.com/microsoftgraph/msgraph-training-changenotifications)an.</span><span class="sxs-lookup"><span data-stu-id="c7690-110">Please provide any feedback on this tutorial in the [GitHub repository](https://github.com/microsoftgraph/msgraph-training-changenotifications).</span></span>
