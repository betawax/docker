FROM php:7.4-fpm
WORKDIR /var/www

RUN apt-get update && apt-get install -y unzip \
libfreetype6-dev libjpeg62-turbo-dev libpng-dev \
&& docker-php-ext-configure gd --with-freetype --with-jpeg \
&& docker-php-ext-install -j$(nproc) bcmath gd mysqli opcache pdo_mysql

COPY --from=composer:latest /usr/bin/composer /usr/local/bin/composer

# Laravel
#RUN printf "#!/usr/bin/env bash\nphp artisan \"\$@\"\n" > /usr/local/bin/artisan && chmod 755 /usr/local/bin/artisan

# WordPress
#COPY --from=wordpress:cli /usr/local/bin/wp /usr/local/bin/wp-cli
#RUN apt-get install -y default-mysql-client less && \
#printf "#!/usr/bin/env bash\nsu - www-data -s /bin/bash -c 'wp-cli \"\$@\"' -- wp-cli \"\$@\"\n" \
#> /usr/local/bin/wp && chmod 755 /usr/local/bin/wp
