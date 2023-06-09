FROM php:8.0-fpm

WORKDIR /php_code

VOLUME ["/php_code"]

COPY --from=mlocati/php-extension-installer /usr/bin/install-php-extensions /usr/local/bin/

RUN install-php-extensions xdebug
RUN docker-php-ext-install pdo 
RUN docker-php-ext-install pdo_mysql
RUN docker-php-ext-install mysqli
RUN docker-php-ext-install exif && docker-php-ext-enable exif

RUN pecl install redis && docker-php-ext-enable redis

RUN apt-get update && apt-get install -y \ 
    libmagickwand-dev --no-install-recommends \ 
    zlib1g-dev libicu-dev g++ \
    && pecl install imagick \ 
    && docker-php-ext-enable imagick 
RUN apt-get -y update \
    && apt-get install -y libicu-dev \ 
    && docker-php-ext-configure intl \
    && docker-php-ext-install intl

RUN docker-php-ext-configure gd && docker-php-ext-install gd

RUN cd /usr/bin && curl -s http://getcomposer.org/installer | php && ln -s /usr/bin/composer.phar /usr/bin/composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer
COPY --from=composer /usr/bin/composer /usr/bin/composer

COPY php.ini /usr/local/etc/php/
COPY . /php_code/