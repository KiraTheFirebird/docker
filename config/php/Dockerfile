FROM php:7.2-fpm

ENV DEBIAN_FRONTEND noninteractive

RUN useradd -ms /bin/bash fenix

RUN apt-get update && apt-get install -y --no-install-recommends libicu-dev libjpeg-dev libpng-dev libfreetype6-dev
RUN docker-php-ext-configure gd --with-png-dir=/usr/include --with-jpeg-dir=/usr/include --with-freetype-dir=/usr/include

RUN docker-php-ext-install pdo_mysql bcmath mbstring opcache zip pcntl intl gd
RUN pecl install xdebug && docker-php-ext-enable xdebug

RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer
RUN apt-get install nano

WORKDIR /src