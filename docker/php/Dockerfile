FROM php:8.4-cli-alpine

RUN apk add --no-cache \
    postgresql-dev \
    icu-dev \
    && docker-php-ext-install \
    pdo \
    pdo_pgsql \
    intl \
    opcache

COPY --from=composer:latest /usr/bin/composer /usr/bin/composer

WORKDIR /var/www/html

EXPOSE 8080
CMD ["php", "-S", "0.0.0.0:8080", "-t", "public"]
