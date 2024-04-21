FROM php:8.1-fpm

ARG USER_UID=1000
ARG USER_GID=${USER_UID}

ADD https://github.com/mlocati/docker-php-extension-installer/releases/latest/download/install-php-extensions /usr/local/bin/

RUN chmod +x /usr/local/bin/install-php-extensions && \
    install-php-extensions \
    apcu \
    bcmath \
    calendar \
    gd \
    gettext \
    intl \
    luasandbox \
    mysqli \
    memcached \
    pcntl \
    pdo_mysql \
    redis \
    shmop \
    soap \
    sockets \
    sysvsem \
    xmlrpc \
    xsl \
    zip \
    opcache \
    excimer \
    xdebug \
    @composer

RUN apt update && apt install -y python3 telnet libvips-tools
