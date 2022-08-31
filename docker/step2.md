Legen Sie ein neues Dockerfile mit dem Editor nano an: `nano Dockerfile`

Kopieren Sie den folgenden Inhalt in das Dockerfile:

```
#Built on latest version of debian
FROM debian:latest

#Updating and/or upgrading the version of debian
RUN apt-get update \
 && apt-get upgrade -y \
 && apt-get install -y apache2

#Opening port 80 for the web server
EXPOSE 80

#Running Apache2 server in foreground
ENTRYPOINT ["apachectl", "-DFOREGROUND"]
```{{copy}}

Sie können die Änderungen mit `CTRL-O` speichern. Mit `CTRL-X` beenden Sie den Editor.

Bauen Sie anschließend das Docker-Image: `docker build -t my-apache .`
Dieser Vorgang wird einige Zeit in Anspruch nehmen.

Sie können sich nun mit `docker images` die Liste aller Images anzeigen lassen. Das Image `my-apache` sollte dort nun aufgeführt sein.

Starten Sie nun einen Container mit diesem Image und geben Sie dabei den Port 80 frei:
`docker run -d --name=my-apache -p 80:80 my-apache`

Sie können den laufenden Apache nun über den folgenden Link erreichen

{{TRAFFIC_HOST1_80}}
