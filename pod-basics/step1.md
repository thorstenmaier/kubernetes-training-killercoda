In dieser Umgebung ein Alias für `kubectl` definiert, so dass der Buchstabe `k` ausreichend ist, um mit kubectl zu arbeiten (`alias k=kubectl`{{exec}}).

Mit `kubectl get pod` können Sie die aktuell laufenden Pods auflisten. Initial sollten keine Pods gestartet sein.

Starten wir nun einen ersten Pod mit einem nginx Container und dem Namen "my-nginx":
`kubectl run --image=nginx my-nginx`

Der Pod ist zunächst nicht von außen erreichbar, so dass wir den korrekten Start im ersten Schritt über das Anzeigen des Logfiles kontrollieren:
`kubectl logs my-nginx`

Um den laufenden Webserver im Browser aufrufen zu können, können wir mit dem Befehl port-forward eine Port-Weiterleitung einrichten:
`kubectl port-forward my-nginx 80:80`
Der Webserver sollte anschließend über den folgenden Link erreichbar sein.

{{TRAFFIC_HOST1_80}}

Eine solche Port-Weiterleitung wird lediglich zu Testzwecken eingesetzt. Die Weiterleitung wird daher mit der Tastenkombination `CTRL-C` abgebrochen.
