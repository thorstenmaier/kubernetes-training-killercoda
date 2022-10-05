Im unten angezeigten Terminal-Fenster können wir die Pod-Definition mit dem folgenden Befehl im Cluster bekannt machen:

`kubectl apply -f my-pod.yaml`

Anschließend können wir mit dem folgenden Befehl den Zustand des gerade erstellten Pods überprüfen. Die Option `-w` steht für "watch" und sorgt dafür, dass wir alle Aktualisierungen automatisch auf der Konsole angezeigt bekommen. Sobald der Pod im Zustand "Running" angekommen ist, können wir den Befehl mit `CTRL-C` beenden:

`kubectl get pod my-nginx -w`

Möchten wir den laufenden Pod über den Browser aufrufen, können wir dies mit einem temporären Port-Forward tun:

`kubectl port-forward --address 0.0.0.0 my-nginx 80:80`

Über das Burger-Menü (drei kleine waagrechte Striche) direkt unter dem Logout-Button gelangen wir ins Menü "Traffic / Ports". Dort können wir dem Link zum Port 80 folgen und sollten den laufenden nginx-Server sehen.

Anschließend beenden wir den laufende Port-Forward-Prozess mit `CTRL-C`.
