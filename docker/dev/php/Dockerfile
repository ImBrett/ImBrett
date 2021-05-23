FROM php:7.4-fpm-alpine
ADD ./docker/dev/php/conf/www.conf /usr/local/etc/php-fpm.d/

# Create the user and group needed to run the application
RUN addgroup -g 1000 imbrett && adduser -G imbrett -g imbrett -s /bin/sh -D imbrett

# Create the applications directory and set permissions
RUN mkdir -p /var/www/html
RUN chown imbrett:imbrett /var/www/html
WORKDIR /var/www/html

# Install postgres dependancies
RUN set -ex \
  && apk --no-cache add \
    postgresql-dev

# Configure postgres extension
RUN docker-php-ext-configure pgsql -with-pgsql=/usr/local/pgsql

# Install postgres drivers
RUN docker-php-ext-install pdo pdo_pgsql
