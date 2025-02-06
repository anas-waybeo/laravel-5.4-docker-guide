FROM php:5.6-fpm

# Use Debian's archive URLs for stretch and remove stretch-updates
RUN sed -i 's/deb.debian.org/archive.debian.org/g' /etc/apt/sources.list && \
    sed -i 's|security.debian.org|archive.debian.org|g' /etc/apt/sources.list && \
    sed -i '/stretch-updates/d' /etc/apt/sources.list && \
    echo 'Acquire::Check-Valid-Until "false";' > /etc/apt/apt.conf.d/99no-check-valid-until && \
    apt-get update && apt-get install -y --no-install-recommends \
    git \
    unzip \
    zip \
    && docker-php-ext-install mysqli pdo pdo_mysql \
    && docker-php-ext-enable pdo_mysql \
    && rm -rf /var/lib/apt/lists/* 
RUN apt-get update && apt-get install -y \
    libxml2-dev \
    && docker-php-ext-install soap

RUN apt-get update && apt-get install -y \
    libssl-dev \
    && pecl install mongo \
    && echo "extension=mongo.so" > /usr/local/etc/php/conf.d/30-mongo.ini    

# Install Composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

# Set working directory
WORKDIR /var/www

# Copy application files
COPY . /var/www

# Set permissions
RUN chown -R www-data:www-data /var/www

EXPOSE 9000

CMD ["php-fpm"]
