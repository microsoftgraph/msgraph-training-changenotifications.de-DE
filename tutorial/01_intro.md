<!-- markdownlint-disable MD002 MD041 -->

In diesem Lernprogramm erfahren Sie, wie Sie eine .net-Kern-app erstellen, die die Microsoft Graph-API zum Empfangen von Benachrichtigungen (webhooks) verwendet, wenn sich ein Benutzerkonto in Azure Active Directory (Azure AD) ändert und Abfragen mithilfe der Delta-Abfrage-API ausführt, um alle Änderungen an Benutzer zu empfangen. Konten seit der letzten Abfrage vorgenommen wurden.

> [!TIP]
> Wenn Sie das fertige Lernprogramm einfach herunterladen möchten, können Sie das GitHub- [Repository](https://github.com/microsoftgraph/msgraph-training-changenotifications)herunterladen oder Klonen.

## <a name="prerequisites"></a>Voraussetzungen

Bevor Sie mit diesem Lernprogramm beginnen, sollten Sie [.net Core 2,2 SDK](https://dotnet.microsoft.com/download) und [Visual Studio Code](https://code.visualstudio.com/) auf Ihrem Entwicklungscomputer installiert haben. Wenn Sie diese nicht installiert haben, besuchen Sie die vorherigen Links für Downloadoptionen.

> [!NOTE]
> Dieses Lernprogramm wurde mit .net Core Version 2,2 geschrieben. Die Schritte in diesem Leitfaden funktionieren möglicherweise mit anderen Versionen, jedoch nicht getestet.

## <a name="feedback"></a>Feedback

Geben Sie Feedback zu diesem Lernprogramm im [GitHub-Repository](https://github.com/microsoftgraph/msgraph-training-changenotifications)an.