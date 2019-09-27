FROM php:7.2-fpm-alpine

LABEL Author="m0yuqi <m0yuqi@126.com>" Blog="http://www.m0yuqi.cn"

RUN sed -i "s/dl-cdn.alpinelinux.org/mirrors.aliyun.com/g" /etc/apk/repositories  &&\
    apk -U upgrade && \
    apk add --no-cache  freetype-dev libjpeg-turbo-dev libpng-dev \
    && docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/ \
    && docker-php-ext-install -j$(nproc) gd \
    && docker-php-ext-install bcmath zip opcache iconv  pdo pdo_mysql mysqli\
    && rm -rf /var/cache/apk/* \
    && rm -rf /var/lib/apk/*
