FROM alpine

RUN sed -i "s/http:\/\/dl-cdn.alpinelinux.org/http:\/\/mirrors.aliyun.com/g" /etc/apk/repositories && \
    apk -U upgrade && \
    apk add --no-cache mariadb mariadb-client mariadb-server-utils pwgen && \
    rm -f /var/cache/apk/*

ADD run.sh /scripts/run.sh
RUN mkdir /docker-entrypoint-initdb.d && \
    mkdir /scripts/pre-exec.d && \
    mkdir /scripts/pre-init.d && \
    chmod -R 755 /scripts

EXPOSE 3306

VOLUME ["/var/lib/mysql"]

ENTRYPOINT ["/scripts/run.sh"]