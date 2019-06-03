FROM alpine:3.8

RUN apk add --update \
    php7.3-fpm \
    php7.3-apcu \
    php7.3-ctype \
    php7.3-curl \
    php7.3-dom \
    php7.3-gd \
    php7.3-iconv \
    php7.3-imagick \
    php7.3-json \
    php7.3-intl \
    php7.3-mcrypt \
    php7.3-fileinfo\
    php7.3-mbstring \
    php7.3-opcache \
    php7.3-openssl \
    php7.3-pdo \
    php7.3-pdo_mysql \
    php7.3-mysqli \
    php7.3-xml \
    php7.3-zlib \
    php7.3-phar \
    php7.3-tokenizer \
    php7.3-session \
    php7.3-simplexml \
    php7.3-xdebug \
    php7.3-zip \
    php7.3-dev \
    php7.3-bcmath \
    php7.3-tidy \
    php7.3-sqlite \
    php7.3-cli \
    make \
    curl

RUN rm -rf /var/cache/apk/* && rm -rf /tmp/* && \
    curl --insecure https://getcomposer.org/composer.phar -o /usr/bin/composer && chmod +x /usr/bin/composer

# https://stackoverflow.com/questions/31369867/how-to-install-php-redis-extension-using-the-official-php-docker-image-approach
RUN pecl install redis && docker-php-ext-enable redis

ADD symfony.ini /etc/php7.3/conf.d/
ADD symfony.ini /etc/php7.3/cli/conf.d/
ADD xdebug.ini  /etc/php7.3/conf.d/

ADD symfony.pool.conf /etc/php7/php-fpm.d/

CMD ["php-fpm7", "-F"]

WORKDIR /var/www/symfony
EXPOSE 9001
