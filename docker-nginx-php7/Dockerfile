#From php:7-fpm-alpine
From dockernginxphp7_php7fpm

RUN apk update
RUN apk add --update curl openssl libintl icu
RUN docker-php-ext-install intl
RUN docker-php-ext-install pdo pdo_mysql mysqli
RUN docker-php-ext-install mbstring gettext soap json
RUN docker-php-ext-install pgsql pdo_pgsql

RUN apk add --update libxml2-dev libmcrypt libmcrypt-dev
RUN docker-php-ext-install mcrypt 
RUN docker-php-ext-install dom

RUN apk add --update libintl
RUN docker-php-ext-install mbstring soap tokenizer

RUN apk add --update libc-dev
RUN apk add --update gettext-dev
RUN docker-php-ext-install gettext

RUN docker-php-ext-install zip

RUN apk add --update curl-dev
RUN docker-php-ext-install curl

RUN docker-php-ext-configure ftp
RUN docker-php-ext-install ftp

RUN docker-php-ext-configure bcmath
RUN docker-php-ext-install bcmath

RUN apk add --update gd-dev libpng-dev freetype-dev libjpeg-turbo-dev
RUN docker-php-ext-configure gd --with-freetype-dir=/usr --with-jpeg-dir=/usr/include/
RUN docker-php-ext-install gd iconv exif

RUN apk add --update imap-dev krb5-dev \
    && docker-php-ext-configure imap --with-imap --with-imap-ssl --with-kerberos \
    && docker-php-ext-install imap

RUN docker-php-ext-intall fileinfo tokenizer ctype json posix phar calendar sockets session  
RUN docker-php-ext-install opcache

RUN apk add --update sqlite-dev && docker-php-ext-install pdo_sqlite

RUN pecl install redis && \
  docker-php-ext-enable redis

RUN apk add --update postgresql-dev && docker-php-ext-install pgsql pdo_pgsql

#install composer
RUN curl -sS https://getcomposer.org/installer | php -- --filename=composer --install-dir=/usr/local/bin

RUN apk add --repository http://dl-cdn.alpinelinux.org/alpine/edge/community --update php7-dev

#phalcon
#RUN curl -LO https://github.com/phalcon/cphalcon/archive/v3.0.2.tar.gz \
#    && tar -zxvf v3.0.2.tar.gz \
#    && cd cphalcon-3.0.2/build \
#    && sh install \
#    && echo "extension=phalcon.so" > /usr/local/etc/php/conf.d/phalcon.ini \
#    && cd ../..
#    && rm -rf v3.0.2.tar.gz cphalcon-3.0.2




RUN rm -rf /var/cache/apk/*


