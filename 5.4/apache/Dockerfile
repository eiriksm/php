FROM php:5.4-apache
MAINTAINER drupal-docker

VOLUME /var/www/html

RUN apt-get update && apt-get install -y libpng12-dev libjpeg-dev libpq-dev \
	&& docker-php-ext-configure gd --with-png-dir=/usr --with-jpeg-dir=/usr \
	&& docker-php-ext-install gd mbstring pdo pdo_mysql pdo_pgsql zip \
	&& pecl install redis \
	&& docker-php-ext-enable redis \
	&& a2enmod rewrite \
	&& rm -rf /var/lib/apt/lists/*

COPY drupal.ini /usr/local/etc/php/conf.d/
