In dieser Übung wollen wir erste Schritte mit YAML in Kubernetes gehen.

Zunächst wechseln wir in die Editor-Ansicht und legen dort eine neue Datei mit dem Namen `my-pod.yaml` an. Im Editor sind verschiedene Templates hinterlegt. Tippe im Editor `Pod`. Es sollte sich eine Auswahlliste mit dem Eintrag `Kubernetes Pod` öffnen. Mit `ENTER` können wir dieses Template in den Editor laden.

Der Cursor blinkt nach der Erstellung an mehreren Stellen. Ersetze den Namen durch `my-nginx`.

Hier die passende Dokumentation zu den einzelnen Stellen:

- `metadata.name`: Name must be unique within a namespace. Is required when creating resources, although some resources may allow a client to request the generation of an appropriate name automatically. Name is primarily intended for creation idempotence and configuration definition. Cannot be updated. More info: <http://kubernetes.io/docs/user-guide/identifiers#names>

- `metadata.label`: Map of string keys and values that can be used to organize and categorize (scope and select) objects. May match selectors of replication controllers and services. More info: <http://kubernetes.io/docs/user-guide/labels>

- `spec.containers.name`: Name of the container specified as a DNS_LABEL. Each container in a pod must have a unique name (DNS_LABEL). Cannot be updated.

Mit der Tab-Taste springst du jeweils zum nächsten Feld, das editiert werden muss:

- `spec.containers.image`: Container image name. More info: <https://kubernetes.io/docs/concepts/containers/images>

Als Image verwenden wir `nginx`.

Die vorerst letzte Einstellung setzt den Port (ggf. mehrere), der geöffnet werden soll:

- `spec.containers.ports`: Number of port to expose on the pod's IP address. This must be a valid port number, 0 < x < 65536.

Hier wählen wir Port `80`.

Die fertige YAML-Datei:

```yaml
apiVersion: v1
kind: Pod
metadata:
  name: my-nginx
  labels:
    name: my-nginx
spec:
  containers:
  - name: my-nginx
    image: nginx
    resources:
      limits:
        memory: "128Mi"
        cpu: "500m"
    ports:
      - containerPort: 80
```
