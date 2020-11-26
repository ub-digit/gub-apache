FROM ubuntu:20.04

ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get update \
  && apt-get install -y apache2 vim less

RUN a2enmod ssl rewrite proxy proxy_http headers

CMD ["apachectl", "-DFOREGROUND", "-e", "debug"]
