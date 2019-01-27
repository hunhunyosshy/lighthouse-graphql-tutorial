FROM php:7.3.1-fpm
COPY php.conf/php.ini /usr/local/etc/php/

# install composer
RUN cd /usr/local/bin && curl -s http://getcomposer.org/installer | php && \
  ln -s /usr/local/bin/composer.phar /usr/local/bin/composer
RUN apt-get update && apt-get install -y \
  git \
  zip \
  unzip \
  vim

RUN apt-get update \
  && apt-get install -y libpq-dev \
  && docker-php-ext-install pdo_mysql

WORKDIR /var/www