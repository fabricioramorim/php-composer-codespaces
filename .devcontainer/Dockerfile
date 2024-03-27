FROM php:8.1-fpm

RUN apt-get update && apt-get install -y \
    git \
    curl \
    vim

COPY php.ini /etc/php/8.1/cli/php.ini

WORKDIR /app

COPY composer.json composer.lock package.json .

RUN composer install

COPY . .

RUN npm install

EXPOSE 80

CMD ["php", "artisan", "serve"]
