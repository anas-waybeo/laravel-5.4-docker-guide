FROM php:8.3-fpm

RUN apt-get update && apt-get install -y \
    libmariadb-dev \
    libicu-dev \
    libzip-dev \
    vim \
    && docker-php-ext-install \
    intl \
    zip \
    pdo \
    sockets \
    pdo_mysql

RUN docker-php-ext-enable pdo_mysql
RUN pecl install mongodb \
    && docker-php-ext-enable mongodb

RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

WORKDIR /var/www/

COPY . .
    
EXPOSE 9000
