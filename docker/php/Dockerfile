FROM php:7.4-fpm-alpine
WORKDIR /var/www

RUN apk upgrade && apk add unzip \
freetype-dev libjpeg-turbo-dev libpng-dev zlib-dev && \
docker-php-ext-configure gd --with-freetype --with-jpeg && \
docker-php-ext-install -j$(nproc) bcmath gd mysqli opcache pdo_mysql

COPY --from=composer:latest /usr/bin/composer /usr/local/bin/composer

# Laravel
#RUN printf "#!/usr/bin/env sh\nphp artisan \"\$@\"\n" > /usr/local/bin/artisan && chmod 755 /usr/local/bin/artisan

# WordPress
#COPY --from=wordpress:cli /usr/local/bin/wp /usr/local/bin/wp-cli
#RUN apk add less mysql-client && \
#printf "#!/usr/bin/env sh\nsu www-data -s /bin/sh -c 'wp-cli \"\$@\"' -- wp-cli \"\$@\"\n" \
#> /usr/local/bin/wp && chmod 755 /usr/local/bin/wp
