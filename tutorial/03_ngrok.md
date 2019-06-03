<!-- markdownlint-disable MD002 MD041 -->

<span data-ttu-id="692eb-101">Damit Microsoft Graph Benachrichtigungen an Ihre Anwendung sendet, die auf dem Entwicklungscomputer ausgeführt werden, müssen Sie ein Tool wie ngrok zum Tunneln von Anrufen aus dem Internet zu Ihrem Computer verwenden.</span><span class="sxs-lookup"><span data-stu-id="692eb-101">In order for the Microsoft Graph to send notifications to your application running on your development machine you need to use a tool such as ngrok to tunnel calls from the internet to your machine.</span></span> <span data-ttu-id="692eb-102">Ngrok ermöglicht, dass Anrufe aus dem Internet an Ihre Anwendung weitergeleitet werden, ohne dass Firewallregeln erstellt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="692eb-102">Ngrok allows calls from the internet to be directed to your application running locally without needing to create firewall rules.</span></span>

<span data-ttu-id="692eb-103">Bevor Sie fortfahren, sollten Sie [ngrok](https://ngrok.com) auf Ihrem Entwicklungscomputer installiert haben.</span><span class="sxs-lookup"><span data-stu-id="692eb-103">Before you continue you should have [ngrok](https://ngrok.com) installed on your development machine.</span></span> <span data-ttu-id="692eb-104">Wenn Sie nicht über ngrok verfügen, besuchen Sie den vorherigen Link zum Herunterladen von Optionen und Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="692eb-104">If you do not have ngrok, visit the previous link for download options and instructions.</span></span>

<span data-ttu-id="692eb-105">Nachdem Sie installiert haben, führen Sie ngrok aus.</span><span class="sxs-lookup"><span data-stu-id="692eb-105">Once installed, run ngrok.</span></span>

```shell
ngrok http 5000
```

<span data-ttu-id="692eb-106">Damit wird ngrok gestartet und Anforderungen von einer externen ngrok-URL an Ihren Entwicklungscomputer an Port 5000 übertragen.</span><span class="sxs-lookup"><span data-stu-id="692eb-106">This will start ngrok and will tunnel requests from an external ngrok url to your development machine on port 5000.</span></span>

<span data-ttu-id="692eb-107">Kopieren Sie die HTTPS-Weiterleitungsadresse.</span><span class="sxs-lookup"><span data-stu-id="692eb-107">Copy the https forwarding address.</span></span> <span data-ttu-id="692eb-108">Im folgenden Beispiel wäre `https://787b8292.ngrok.io`.</span><span class="sxs-lookup"><span data-stu-id="692eb-108">In the example below that would be `https://787b8292.ngrok.io`.</span></span> <span data-ttu-id="692eb-109">Dies wird später erforderlich sein.</span><span class="sxs-lookup"><span data-stu-id="692eb-109">You will need this later.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="692eb-110">Jedes Mal, wenn ngrok neu gestartet wird, wird eine neue Adresse generiert, die Sie erneut kopieren müssen.</span><span class="sxs-lookup"><span data-stu-id="692eb-110">Each time ngrok is restarted a new address will be generated and you will need to copy it again.</span></span>

```shell
ngrok by @inconshreveable

Session Status                online
Account                       Basic
Version                       2.3.15
Region                        United States (us)
Web Interface                 http://127.0.0.1:4040
Forwarding                    http://787b8292.ngrok.io -> http://localhost:5000
Forwarding                    https://787b8292.ngrok.io -> http://localhost:5000

Connections                   ttl     opn     rt1     rt5     p50     p90
                              0       0       0.00    0.00    0.00    0.00
```
