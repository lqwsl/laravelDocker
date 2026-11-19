FROM php:8.4-fpm


# Системные зависимости
RUN apt-get update && apt-get install -y \
    git \
    curl \
    libpng-dev \
    libonig-dev \
    libxml2-dev \
    libzip-dev \
    zip \
    unzip \
    && apt-get clean && rm -rf /var/lib/apt/lists/*


# Расширения PHP для Laravel и MySQL
RUN docker-php-ext-install pdo_mysql mbstring exif pcntl bcmath gd zip


# Установка Composer из официального образа
COPY --from=composer:latest /usr/bin/composer /usr/bin/composer


WORKDIR /var/www