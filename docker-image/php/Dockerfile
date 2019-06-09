FROM php:7.3-fpm-alpine

ARG USER_NAME
ARG USER_UID

# 一時ファイル追加
COPY tmp/* /tmp/

# intファイル追加
COPY php.ini /usr/local/etc/php/php.ini

# リモートリポジトリのアップデート
RUN apk update --no-cache

# ユーザー追加
RUN adduser ${USER_NAME} -u ${USER_UID} -D

# サーバータイムゾーン変更
RUN apk add --no-cache tzdata && \
    ln -sf /usr/share/zoneinfo/Asia/Tokyo /etc/localtime

# 必要なパッケージのインストールとエクステンション追加
RUN apk add \
        gettext \
        bash \
        git \
        sudo \
        curl \
        libxml2-dev \
        openssl-dev \
        libpng \
        libpng-dev \
        libjpeg-turbo-dev \
        libwebp-dev \
        zlib-dev \
        libxpm-dev && \
    docker-php-ext-install pdo pdo_mysql mbstring gd && \
    apk del libpng-dev

# php-fpm設定追加
RUN envsubst < /tmp/zzz-docker.conf > /usr/local/etc/php-fpm.d/zzz-docker.conf

# composer install
RUN curl -sS https://getcomposer.org/installer | php && \
    mv composer.phar /usr/local/bin/composer && \
    composer self-update
