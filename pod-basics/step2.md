In diesem Schritt wollen wir etwas mehr über den gestarteten Pod erfahren. Zunächst können wir hierzu wir den Befehl `describe` verwenden. Besonders interessant ist dabei die Liste der Events am Ende der Ausgabe. Im Fehlerfall würde sich hier unter anderem erkennen lassen, dass das angegebene Image nicht geladen werden konnte:

`kubectl describe pod my-nginx`

Die Ausgabe von `describe` ist sehr sprechend gestaltet. Kubernetes verwaltet die Informationen zu einem Pod intern in einer Datenbank. Mit dem folgenden Befehl können wir die dort abgelegten Daten im YAML-Format anzeigen.

`kubectl get pod my-nginx -o yaml`
