<!-- markdownlint-disable MD002 MD041 -->

Damit Microsoft Graph Benachrichtigungen an Ihre Anwendung sendet, die auf dem Entwicklungscomputer ausgeführt werden, müssen Sie ein Tool wie ngrok verwenden, um Anrufe aus dem Internet an Ihren Entwicklungscomputer zu übertragen. Ngrok ermöglicht, dass Anrufe aus dem Internet an Ihre Anwendung weitergeleitet werden, ohne dass Firewallregeln erstellt werden müssen.

Bevor Sie fortfahren, sollten Sie [ngrok](https://ngrok.com) auf Ihrem Entwicklungscomputer installiert haben. Wenn Sie nicht über ngrok verfügen, besuchen Sie den vorherigen Link zum Herunterladen von Optionen und Anweisungen.

Führen Sie ngrok aus, indem Sie den folgenden Befehl über die Befehlszeile ausführen:

```shell
ngrok http 5000
```

Damit wird ngrok gestartet und Anforderungen von einer externen ngrok-URL an Ihren Entwicklungscomputer an Port 5000 übertragen.

Kopieren Sie die HTTPS-Weiterleitungsadresse. Im folgenden Beispiel wäre `https://787b8292.ngrok.io`. Dies wird später erforderlich sein.

> [!IMPORTANT]
> Jedes Mal, wenn ngrok neu gestartet wird, wird eine neue Adresse generiert, die Sie erneut kopieren müssen.

```shell
ngrok by @inconshreveable

Session Status                online
Account                       ???? ???? (Plan: Free)
Version                       2.3.15
Region                        United States (us)
Web Interface                 http://127.0.0.1:4040
Forwarding                    http://787b8292.ngrok.io -> http://localhost:5000
Forwarding                    https://787b8292.ngrok.io -> http://localhost:5000

Connections                   ttl     opn     rt1     rt5     p50     p90
                              0       0       0.00    0.00    0.00    0.00
```
