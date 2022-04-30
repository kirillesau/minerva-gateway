# Minerva-Gateway

## Beschreibung

Mit dem Gateway sollen bereits vorhandene sowie zukünftige Applikationen des Projekts einheitlich
durch [Keycloak](https://www.keycloak.org/) abgesichert und durch den Loadbalancer geroutet werden. Service Discovery,
sowie die Bereitstellung der Properties übernimmt die Software [Consul](https://www.consul.io/).

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

## Disclaimer

Die verwendeten Lösungen in diesem Projekt müssen für die Aufgabenstellung nicht zwingend Sinn ergeben. In erster Linie
dient dieses Projekt dazu gelernte Themen in der Praxis anzuwenden.

## Lizenz

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details.