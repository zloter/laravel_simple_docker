FROM php:7.4-fpm
ARG TIMEZONE

RUN apt-get update && apt-get install -y git unzip openssl procps acl zlib1g-dev libzip-dev  libicu-dev libpng-dev

# Install Composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer
RUN composer --version

# Set timezone
RUN ln -snf /usr/share/zoneinfo/${TIMEZONE} /etc/localtime && echo ${TIMEZONE} > /etc/timezone
RUN printf '[PHP]\ndate.timezone = "%s"\n', ${TIMEZONE} > /usr/local/etc/php/conf.d/tzone.ini

# Install extensions
RUN docker-php-ext-install  pdo_mysql
RUN docker-php-ext-install  bcmath 
RUN docker-php-ext-install  zip 
RUN docker-php-ext-install  intl 
RUN docker-php-ext-install  sockets 
RUN docker-php-ext-install  gd

WORKDIR /var/www/laravel
