FROM php:8.0-fpm


RUN apt-get update
RUN apt-get install -y \
curl \
wget \
git \
zip

RUN docker-php-ext-install -j$(nproc) iconv mysqli pdo_mysql

RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

ADD php-ini-overrides.ini /usr/local/etc/php/conf.d/40-custom.ini

WORKDIR /application

CMD ["php-fpm"]
