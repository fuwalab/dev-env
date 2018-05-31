FROM php:7.2-fpm-alpine
RUN apk --no-cache add zlib-dev \
    && docker-php-ext-install zip pdo_mysql mysqli

# install composer
RUN php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');" \
    && php composer-setup.php --install-dir=/usr/local/bin --filename=composer \
    && php -r "unlink('composer-setup.php');"

#RUN composer global require "laravel/installer"

#ENV PATH $PATH:/root/.composer/vendor/bin

#WORKDIR /var/www/html/php/
#RUN laravel new laravel

#CMD php artisan serve