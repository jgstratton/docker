FROM alpine:3.8

RUN apk update \
  && apk upgrade \ 
  && apk add --no-cache mysql-client

COPY ./backup.sh /usr/local/bin/backup.sh
COPY ./crontab /var/spool/cron/crontabs/root

RUN chmod u+x /usr/local/bin/backup.sh

ENTRYPOINT ["crond", "-f"]