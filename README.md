# GUB-Apache2

Apache2-server för reverse-proxying av containers.

## Att bygga och pusha imagen

```bash
docker build -t docker.ub.gu.se/gub-apache2:release-202Y.MM.XXX ./apache/
docker login docker.ub.gu.se
docker push docker.ub.gu.se/gub-apache2:release-202Y.MM.XXX
```

## Start av tjänsten med docker-compose

```bash
docker-compose up -d
```

## Starta om tjänsten efter instalation och efter att konfigurationen ändrats

```bash
docker exec -it gub-apache_apache_1 apachectl -k restart -DFOREGROUND
```

'gub-apache_apache_1' är det namn som genererats åt containern vid uppstart.
