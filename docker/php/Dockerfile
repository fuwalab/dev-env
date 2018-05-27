FROM php:5.6-fpm-alpine
RUN docker-php-ext-install pdo_mysql mysqli mbstring

# install composer
RUN php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');" \
  && php composer-setup.php --install-dir=/usr/local/bin --filename=composer \
  && php -r "unlink('composer-setup.php');"
