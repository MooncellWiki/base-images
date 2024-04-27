FROM ghcr.io/mooncellwiki/php:latest

ADD https://github.com/mlocati/docker-php-extension-installer/releases/latest/download/install-php-extensions /usr/local/bin/

RUN mv /usr/local/etc/php/conf.d/php.ini /usr/local/etc/php/conf.d/php.ini2
RUN install-php-extensions \
    xdebug
RUN mv /usr/local/etc/php/conf.d/php.ini2 /usr/local/etc/php/conf.d/php.ini