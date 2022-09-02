Mit `kubectl get pod` lässt sich erkennen, dass der gestarte Pod nach wie vor aktiv ist. Vor dem Ende des Szenarios möchten wir daher ein wenig Aufräumen und den zuvor gestarteten Pod wieder beenden. Dies geschieht über das Löschen der zuvor angelegten Pod-Resource:

`kubectl delete pod my-nginx`

Ein Aufruf von `kubectl get all` zeigt abschließend, dass nur noch der kubernetes service übrig geblieben ist.
