FROM php:8.0-fpm-alpine
#FROM php:7.4-fpm-alpine
WORKDIR /var/www

# Install common extensions
RUN apk update && apk add unzip \
freetype-dev libjpeg-turbo-dev libpng-dev zlib-dev && \
docker-php-ext-configure gd --with-freetype --with-jpeg && \
docker-php-ext-install -j$(nproc) bcmath gd mysqli opcache pdo_mysql

# Install Composer globally
COPY --from=composer:latest /usr/bin/composer /usr/local/bin/composer

#
# Laravel
#

# Create an alias for the Laravel CLI that will work via "docker compose exec php artisan"
#RUN printf "#!/usr/bin/env sh\nphp artisan \"\$@\"\n" > /usr/local/bin/artisan && chmod 755 /usr/local/bin/artisan

#
# WordPress
#

# Install the WordPress CLI and its required packages
#COPY --from=wordpress:cli /usr/local/bin/wp /usr/local/bin/wp-cli
#RUN apk add less mysql-client

# Create an alias for the WordPress CLI that will work via "docker compose exec php wp"
#RUN printf "#!/usr/bin/env sh\nsu www-data -s /bin/sh -c 'wp-cli \"\$@\"' -- wp-cli \"\$@\"\n" \
#> /usr/local/bin/wp && chmod 755 /usr/local/bin/wp
