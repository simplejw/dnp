FROM php:7.2-fpm

COPY ./sources.list.stretch /etc/apt/sources.list

RUN apt-get update && apt-get install -y libmagickwand-dev --no-install-recommends \
    && apt-get install -y  libfreetype6-dev \
        libjpeg62-turbo-dev \
        libpng-dev \
        libicu-dev \
        libxml2-dev \
        g++ \
    && docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/ \
    && docker-php-ext-install -j$(nproc) gd \
    && pecl install imagick-3.4.3 \
    && pecl install redis-4.1.0 \
    && pecl install apcu \
    && docker-php-ext-enable apcu redis  \
    && docker-php-ext-enable imagick \
    #&& pecl install mongodb \
    #&& docker-php-ext-enable mongodb \
    #&& :\
    && docker-php-ext-install soap \
    #&& docker-php-ext-install iconv \
    && docker-php-ext-install pdo_mysql \
    && docker-php-ext-install intl \
    && docker-php-ext-install zip \
    && docker-php-ext-install opcache \
    && docker-php-ext-install sockets \
    && docker-php-ext-install exif \
    && apt-get autoremove \
    && apt-get clean
    
    
     
