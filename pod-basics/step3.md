Ähnlich wie bei Docker können wir Befehle im Container des Pods ausführen. Dies geschieht mit dem Befehl `exec`. Der eigentliche Befehl wird mit zwei Minuszeichen (`--`) angetrennt. Zusätzlich können wir mit der Option  `-it` ein "interaktives Terminal" bekommen. Zusammengesetzt können wir somit dem folgenden Befehl eine interaktive Shell im Container des Pods bekommen.

`kubectl exec my-nginx -it -- sh`

Schauen wir uns im Container ein wenig um. Zum Beispiel können wir mit den folgenden Befehlen erkennen, dass die Log-Ausgaben von nginx auf `stdout` und `stderr` umgeleitet werden. Dies ist der Grund warum wir von außen mit `kubectl logs` auf die Logs des Webservers zugreifen können:

```shell
cd /var/log/nginx
ls -la
```{{copy}}

Mit dem Befehl `exit` können wir den Pod wieder verlassen.
