# GUB-Apache

Apache server for reverse proxying web containers.

## Att bygga och pusha imagen

Exempel: 

```bash
docker build -t docker.ub.gu.se/gub-apache2:release-202Y.MM.XXX .
```

eller ändra till önskad image-tag i docker-compose.yml och kör sedan:

```bash
docker-compose build
docker login docker.ub.gu.se
docker push docker.ub.gu.se/gub-apache2:release-202Y.MM.XXX
```

## Exempel på start av tjänsten

###  Start med docker run

```bash
docker run -it --rm --name gub-apache --net host -v /opt/apache/sites:/etc/apache2/sites-enabled -v /opt/apache/log:/var/log/apache2 -v /opt/apache/cert:/var/tmp/apache-cert docker.ub.gu.se/gub-apache2:release-2020.11.001

```

### Start med docker-compose

```bash
docker-compose up -d
```

## Starta om tjänsten efter instalation och efter att konfigurationen ändrats

```bash
docker exec -it gub-apache apachectl -k restart -DFOREGROUND
```
