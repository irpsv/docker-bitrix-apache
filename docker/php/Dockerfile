FROM php:7.4-apache-buster

# устанавливаем UID:GID локального пользователя, чтобы не было проблем с правами при шаринге папок
# только на локальной машине, на проде не нужно
RUN usermod -u 1000 www-data && \
    groupmod -g 1000 www-data

RUN apt-get update && apt-get install -y \
    libfreetype6-dev \
    libzip-dev \
    libjpeg-dev \
    libwebp-dev \
    zip

RUN docker-php-ext-configure gd --enable-gd --with-freetype --with-jpeg --with-webp

RUN docker-php-ext-install \
    opcache \
    pdo \
    pdo_mysql \
    mysqli \
    zip \
    gd
