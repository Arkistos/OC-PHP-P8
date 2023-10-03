FROM php:5.6.40-apache

RUN curl -sSk https://getcomposer.org/installer | php -- --disable-tls && \
   mv composer.phar /usr/local/bin/composer

COPY . /var/www/

COPY ./docker/apache.conf /etc/apache2/sites-available/000-default.conf

RUN cd /var/www && \
    composer install

RUN cd /var/www && \
    chmod -R 777 var/cache var/logs var/sessions

WORKDIR /var/www/

EXPOSE 80
