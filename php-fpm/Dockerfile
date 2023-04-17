######
# See: https://hub.docker.com/_/php/
######

FROM php:8.1-fpm

######
# You can install php extensions using docker-php-ext-install
######

RUN apt-get update && apt-get install -y \
		libfreetype6-dev \
		libjpeg62-turbo-dev \
		libpng-dev \
	&& docker-php-ext-configure gd --with-freetype --with-jpeg \
	&& docker-php-ext-install -j$(nproc) gd

RUN docker-php-ext-install -j$(nproc) mysqli

RUN apt-get install -y \
        libzip-dev \
        zip \
  && docker-php-ext-install zip
