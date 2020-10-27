FROM php:7.2-fpm

COPY --from=mlocati/php-extension-installer /usr/bin/install-php-extensions /usr/bin/


RUN apt-get update && apt-get install libssh-dev unzip

RUN install-php-extensions  gd exif imagick redis apcu mongodb soap pdo_mysql intl zip opcache sockets amqp mcrypt oauth rdkafka bcmath

RUN curl -sS https://getcomposer.org/installer | php \
    && mv composer.phar /usr/local/bin/composer \
    && chmod +x /usr/local/bin/composer