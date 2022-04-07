FROM php:7.4-fpm

RUN apt-get update && apt-get install -y libssh-dev unzip git wget

COPY --from=mlocati/php-extension-installer /usr/bin/install-php-extensions /usr/bin/

RUN install-php-extensions bz2 gettext xsl gd exif imagick redis apcu mongodb soap pdo_mysql intl zip opcache sockets amqp mcrypt oauth rdkafka bcmath mysqli xmlrpc swoole uuid xdebug

RUN curl -sS https://getcomposer.org/installer | php \
    && mv composer.phar /usr/local/bin/composer \
    && chmod +x /usr/local/bin/composer