FROM php:7.2-fpm-alpine

LABEL Author="m0yuqi <m0yuqi@126.com>" Blog="http://www.m0yuqi.cn"

RUN sed -i "s/http:\/\/dl-cdn.alpinelinux.org/http:\/\/mirrors.aliyun.com/g" /etc/apk/repositories && \
    apk -U upgrade && \
    apk add --no-cache php7-pdo_sqlite \
    sqlite \
    php7-sqlite3 \
    php7-tokenizer \
    php7-ctype && \
    mkdir /www && \
    chmod -R 777 /www
