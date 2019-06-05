FROM alpine:3.9
ADD https://dl.bintray.com/php-alpine/key/php-alpine.rsa.pub /etc/apk/keys/php-alpine.rsa.pub
RUN apk --update add ca-certificates
RUN echo "https://dl.bintray.com/php-alpine/v3.9/php-7.3" >> /etc/apk/repositories

#
# PHP Stuff
#
RUN apk add --update php
RUN apk add --update \
    php-fpm \
    php-apcu \
    php-ctype \
    php-curl \
    php-dom \
    php-gd \
    php-iconv \
    php-imagick \
    php-json \
    php-intl \
    #php-mcrypt \
    php-fileinfo\
    php-mbstring \
    php-opcache \
    php-openssl \
    php-pdo \
    php-pdo_mysql \
    php-xml \
    php-zlib \
    php-phar \
    php-tokenizer \
    php-session \
    php-xdebug \
    php-zip \
    #php-dev \
    php-bcmath \
    php-tidy \
    php-cli \
    php-pear \
    php-redis \
    make \
    curl

#
# Cache + Composer
#
RUN rm -rf /var/cache/apk/* && rm -rf /tmp/* && \
    curl --insecure https://getcomposer.org/composer.phar -o /usr/bin/composer && chmod +x /usr/bin/composer

#
# Copy config
#
ADD symfony.ini /etc/php7/conf.d/
ADD symfony.ini /etc/php7/cli/conf.d/
ADD xdebug.ini  /etc/php7/conf.d/
ADD symfony.pool.conf /etc/php7/php-fpm.d/
CMD ["php-fpm7", "-F"]

#
# Fin
#
WORKDIR /var/www/xivapi
EXPOSE 9001
