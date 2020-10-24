FROM php:7.2-fpm

COPY --from=mlocati/php-extension-installer /usr/bin/install-php-extensions /usr/bin/

RUN install-php-extensions gd exif imagick redis apcu mongodb soap pdo_mysql intl zip opcache sockets
