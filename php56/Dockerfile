FROM php:5.6-fpm
MAINTAINER fei <fei.liu@mdpi.com>

#ENV DEBIAN_FRONTEND=noninteractive

#COPY sources.list /etc/apt/sources.list

RUN apt-get update && apt-get install -y \
    libmcrypt-dev libpng12-dev libfreetype6-dev libjpeg62-turbo-dev librabbitmq-dev libsasl2-dev libxml2-dev curl \
    libcurl3 libcurl3-dev libxslt-dev libmagickwand-dev --no-install-recommends \
    && docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-gd-dir=/usr/include/ \
    && docker-php-ext-install gd iconv mcrypt mbstring mysqli pdo pdo_mysql zip simplexml xml xsl dom ctype xmlrpc \
    session json curl exif gettext opcache \
    && pecl install imagick \
    && docker-php-ext-enable imagick \
    && pecl install xdebug \
    && echo "zend_extension=$(find /usr/local/lib/php/extensions/ -name xdebug.so)" > /usr/local/etc/php/conf.d/xdebug.ini \
    && echo "xdebug.remote_enable=on" >> /usr/local/etc/php/conf.d/xdebug.ini \
    && echo "xdebug.remote_autostart=off" >> /usr/local/etc/php/conf.d/xdebug.ini \
    && rm -rf /var/cache/apt/* /var/lib/apt/lists/*

COPY ./php.ini /usr/local/etc/php/conf.d/