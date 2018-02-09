FROM php:7.0-fpm

RUN apt-get update && \
    apt-get install -y \
        zlib1g-dev libpng-dev

RUN docker-php-ext-install pdo_mysql

RUN docker-php-ext-install mbstring

RUN docker-php-ext-install zip

RUN docker-php-ext-install gd

RUN docker-php-ext-install json

RUN yes | pecl install xdebug \
    && echo "zend_extension=$(find /usr/local/lib/php/extensions/ -name xdebug.so)" > /usr/local/etc/php/conf.d/xdebug.ini \
    && echo "xdebug.remote_enable=on" >> /usr/local/etc/php/conf.d/xdebug.ini \
    && echo "xdebug.remote_autostart=off" >> /usr/local/etc/php/conf.d/xdebug.ini \
    && echo "xdebug.profiler_enable_trigger=on" >> /usr/local/etc/php/conf.d/xdebug.ini

RUN echo "disable_functions = mail" >> /usr/local/etc/php/php.ini