FROM php:7.4-apache

WORKDIR /var/www/html

RUN apt-get update && apt-get install -y git libzip-dev zip && docker-php-ext-install mysqli pdo pdo_mysql zip && a2enmod rewrite && chmod -R 755 /var/www/html && chown -R www-data:www-data /var/www && mv "$PHP_INI_DIR/php.ini-production" "$PHP_INI_DIR/php.ini" && git clone git://git.moodle.org/moodle.git . && git branch -a && git branch --track MOODLE_39_STABLE origin/MOODLE_39_STABLE && git checkout MOODLE_39_STABLE

COPY htaccess.txt .htaccess

EXPOSE 80
