FROM php:7.2-fpm
MAINTAINER Shiva SIVANESARAJAH <shiva.srajah@gmail.com>

RUN apt-get update && \
  apt-get -y install \
  # Installation de curl pour télécharger composer
  curl \
  # Installation de git & zip pour le bon fonctionnement de composer
  git \
  zip

RUN curl -sS https://getcomposer.org/installer | php \
  && mv composer.phar /usr/local/bin/ \
  && ln -s /usr/local/bin/composer.phar /usr/local/bin/composer

RUN /usr/local/bin/composer create-project laravel/laravel /var/www/html --prefer-dist
RUN /bin/chown www-data:www-data -R /var/www/html/
