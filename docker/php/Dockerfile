# Use the official PHP 8.4 FPM image as the base image
FROM php:8.4-fpm

RUN apt-get update \
    && apt-get install -y librabbitmq-dev git\
    && docker-php-ext-install mysqli pdo pdo_mysql \
    && docker-php-ext-enable pdo_mysql \
    && pecl install amqp \
    && docker-php-ext-enable amqp

COPY --from=composer /usr/bin/composer /usr/bin/composer