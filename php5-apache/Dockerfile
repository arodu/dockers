# Base image
FROM webdevops/php-apache-dev:5.6

# Fix debconf warnings upon build
#ARG DEBIAN_FRONTEND=noninteractive

# Run apt update and install some dependancies needed for docker-php-ext
RUN apt update

RUN apt install -y apt-utils sendmail mariadb-client \
  pngquant unzip zip libpng-dev libmcrypt-dev git curl libicu-dev \
  libxml2-dev libssl-dev sqlite libpq-dev

#RUN apt install -y postgresql-client

# Install PHP extensions
# RUN docker-php-ext-install mysqli bcmath gd intl xml curl pdo_mysql pdo_sqlite hash zip dom session opcache
RUN docker-php-ext-install gd intl pdo pdo_mysql pdo_pgsql pgsql mysqli

# Update web root to public
# See: https://hub.docker.com/_/php#changing-documentroot-or-other-apache-configuration
#ENV APACHE_DOCUMENT_ROOT /var/www/html/public
#RUN sed -ri -e 's!/var/www/html!${APACHE_DOCUMENT_ROOT}!g' /etc/apache2/sites-available/*.conf
#RUN sed -ri -e 's!/var/www/!${APACHE_DOCUMENT_ROOT}!g' /etc/apache2/apache2.conf /etc/apache2/conf-available/*.conf

# Enable mod_rewrite
#RUN a2enmod rewrite
