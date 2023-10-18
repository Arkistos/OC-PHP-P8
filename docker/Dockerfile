FROM php:7.3.33-apache


###RUN apk add --update --no-cache libgd libpng-dev libjpeg-turbo-dev freetype-dev

RUN docker-php-ext-install -j$(nproc) pdo pdo_mysql

RUN curl -sSk https://getcomposer.org/installer | php -- --disable-tls && \
   mv composer.phar /usr/local/bin/composer


### COPY . /var/www/

COPY ./apache.conf /etc/apache2/sites-available/000-default.conf


### RUN cd /var/www && \
##    composer install

###RUN cd /var/www && \
###    chmod -R 777 var/cache var/logs var/sessions

WORKDIR /var/www/

