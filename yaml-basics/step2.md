Im unten angezeigten Terminal-Fenster können wir die Pod-Definition mit dem folgenden Befehl im Cluster bekannt machen:

`kubectl apply -f my-pod.yaml`

Anschließend können wir mit dem folgenden Befehl den Zustand des gerade erstellten Pods überprüfen. Die Option `-w` steht für "watch" und sorgt dafür, dass wir alle Aktualisierungen automatisch auf der Konsole angezeigt bekommen. Sobald der Pod im Zustand "Running" angekommen ist, können wir den Befehl mit `CTRL-C` beenden:

`kubectl get pod my-nginx -w`

Möchten wir den laufenden Pod über den Browser aufrufen, können wir dies mit einem temporären Port-Forward tun:

`kubectl port-forward --address 0.0.0.0 my-nginx 80:80`

Auch hier wird der laufende Prozess mit `CTRL-C` beendet.
