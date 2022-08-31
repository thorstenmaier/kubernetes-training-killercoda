Mit `docker ps` können Sie die Liste der laufenden Docker Container sehen.

Stoppen Sie nun den noch laufenden Apache-Container mit `docker stop my-apache`.

Kontrollieren Sie erneut mit `docker ps`, ob das Stoppen erfolgeich war.

Ein gestoppter Container wird nicht automatisch entfernt. Mit `docker ps -a` können Sie sehen, dass der Container weiterhin vorhanden ist. Entfernen Sie den Container abschließend mit `docker rm my-apache`.
