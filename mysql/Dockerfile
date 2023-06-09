FROM mysql:latest

RUN mkdir /var/lib/mysql-no-volume

CMD ["--datadir", "/var/lib/mysql-no-volume"]

WORKDIR sql

VOLUME ["/sql"]
