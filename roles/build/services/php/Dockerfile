FROM php:7.3-fpm

WORKDIR /app

RUN apt-get update && \
    apt-get install -y apt-utils curl libzip-dev zip unzip \
    zlib1g zlib1g-dev libxml2-dev libpng-dev libjpeg-dev libcurl4-gnutls-dev libfreetype6-dev libmagickwand-dev && \
    pecl install imagick && \
    docker-php-ext-enable imagick && \
    pecl install redis && \
    docker-php-ext-enable redis && \
    docker-php-ext-install pdo pdo_mysql json mysqli && \
    docker-php-ext-enable mysqli && \
    docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/ && \
    docker-php-ext-install gd && \
    docker-php-ext-install exif && \
    docker-php-ext-install sockets && \
    docker-php-ext-install soap && \
    docker-php-ext-install zip

COPY ./php-ini-overrides.ini /usr/local/etc/php/conf.d/00-php.ini