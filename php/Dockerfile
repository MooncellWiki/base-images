FROM php:8.1.33-fpm
ENV TZ=Asia/Shanghai

RUN mv "$PHP_INI_DIR/php.ini-production" "$PHP_INI_DIR/php.ini"

ADD https://github.com/mlocati/docker-php-extension-installer/releases/download/2.9.11/install-php-extensions /usr/local/bin/

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
    @composer

RUN apt update && apt install -y python3 telnet libvips-tools

COPY ./config/php.ini /usr/local/etc/php/conf.d/php.ini

COPY ./config/php-fpm.conf /usr/local/etc/php-fpm.d/zzz-docker.conf