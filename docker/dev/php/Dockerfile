FROM php:7.4-fpm-alpine
ADD ./docker/dev/php/conf/www.conf /usr/local/etc/php-fpm.d/
RUN addgroup -g 1000 imbrett && adduser -G imbrett -g imbrett -s /bin/sh -D imbrett
RUN mkdir -p /var/www/html
RUN chown imbrett:imbrett /var/www/html
WORKDIR /var/www/html
RUN docker-php-ext-install pdo pdo_mysql
