FROM php:7.2-fpm-alpine

# cf. php-alpineコンテナにxdebugをインストールする時にハマったメモ https://qiita.com/ucan-lab/items/fbf021bf69896538e515

RUN touch /var/log/php_error.log && \
    chown www-data: /var/log/php_error.log && \
    cp /usr/local/etc/php/php.ini-development /usr/local/etc/php/php.ini && \
    apk add autoconf build-base && \
    pecl install xdebug && \
    docker-php-ext-enable xdebug


COPY conf/php-fpm.d/zzz-myconf.conf /usr/local/etc/php-fpm.d/
COPY conf/php.d/myxdebug.ini /usr/local/etc/php/conf.d/

