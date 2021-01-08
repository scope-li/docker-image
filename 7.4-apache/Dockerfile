FROM php:7.4-apache
LABEL maintainer="Scope GmbH <info@scope.li>"

# Install tools and libs.
RUN apt-get update \
    && apt-get install -y --no-install-recommends curl unzip git nano libfreetype6-dev libjpeg62-turbo-dev libpng-dev libzip-dev libicu-dev \
    && docker-php-ext-configure gd --with-freetype --with-jpeg \
    && docker-php-ext-install gd mysqli pdo_mysql zip opcache intl \
    && pecl install xdebug \
    && curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer \
    && rm -rf /var/lib/apt/lists/*
