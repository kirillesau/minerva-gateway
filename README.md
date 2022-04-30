# Minerva-Gateway

## Docker Image bauen und nach Docker Hub pushen

Um ein Image nach [Docker Hub](https://hub.docker.com/) zu pushen wird ein entsprechender Account benötigt. Wichtig ist,
dass man sich auf dem System, von dem ein Image gepushed werden soll, zuvor mit dem Account eingeloggt hat. Ein Beispiel
Login ist im nachfolgenden Befehl zu sehen (mehr Informationen
sind [hier](https://docs.docker.com/engine/reference/commandline/login/) zu finden) :

``` 
docker login -u <username> -p <password>
```

Um ein aktuelles Image zu erzeugen, muss die Anwendung mit `mvn clean package` zuvor gebaut werden. Die Erstellung des
Image's selbst erfolgt durch den Befehl `mvn docker:build`. Zum Schluss muss der Befehl `mvn docker:push` ausgeführt
werden, damit das Image zum Docker Hub gepushed wird. Der nachfolgende Befehl zeigt, wie die Schritte alle auf einmal
ausgeführt werden können.

```
mvn clean package docker:build docker:push
```