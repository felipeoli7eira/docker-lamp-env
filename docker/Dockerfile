FROM php:8.1-apache

RUN a2enmod rewrite

WORKDIR /var/www/html


RUN apt-get update && apt-get install -y \
    git \
    unzip \
    libzip-dev

#     curl \
#     libpng-dev \
#     libonig-dev \
#     libxml2-dev \
#     zip \

# RUN apt-get update && apt-get install -y \
#     php7.1 \
#     php7.1-fpm \
#     php7.1-cli \
#     php7.1-common \
#     php7.1-json \
#     php7.1-opcache \
#     php7.1-mysql \
#     php7.1-mbstring \
#     php7.1-gd \
#     php7.1-imap \
#     php7.1-ldap \
#     php7.1-dev \
#     php7.1-intl \
#     php7.1-gd \
#     php7.1-curl \
#     php7.1-zip \
#     php7.1-xml \
#     curl
RUN docker-php-ext-install pdo pdo_mysql

COPY --from=composer:latest /usr/bin/composer /usr/local/bin/composer
RUN composer install

EXPOSE 80