FROM php:7.2-fpm

RUN apt-get update && apt-get install -y \
        libfreetype6-dev \
        libjpeg62-turbo-dev \
        libpng-dev \
        libicu-dev \
        g++ \
    && docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/ \
    && docker-php-ext-install -j$(nproc) gd \
    && :\    
    && docker-php-ext-install iconv \
    && docker-php-ext-install pdo_mysql \
    && docker-php-ext-install intl \
    && docker-php-ext-install zip \
    && docker-php-ext-install opcache \
    && docker-php-ext-install sockets \
    && docker-php-ext-install exif \
    && :\
    && apt-get install -y libxml2-dev \
    && docker-php-ext-install soap \
    && :\
    && pecl install redis \
    && docker-php-ext-enable redis \
    && :\
    && pecl install apcu \
    && docker-php-ext-enable apcu \
    && :\
    && pecl install mongodb \
    && docker-php-ext-enable mongodb \
    && :\
    && apt-get install -y --no-install-recommends libmagickwand-dev \
    && pecl install imagick \
    && docker-php-ext-enable imagick 
