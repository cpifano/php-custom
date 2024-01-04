# ------------------------------------------------------------------------------------- #
# PHP CUSTOM BUILD:
# ------------------------------------------------------------------------------------- #
# docker build -t cpifano/php-custom:1.0.0 -f docker/Dockerfile .
# ------------------------------------------------------------------------------------- #
FROM php:5.6-apache

LABEL version="1.0.0"
LABEL author="Camilo Pifano Herrera <camilopifano@gmail.com>"
LABEL description="PHP Custom is a docker image of an old version of PHP (5.6) with old dependencies already resolved"

# Set port:
EXPOSE 80

# Debian 9/stretch moved to archive.debian.org:
RUN echo "deb http://archive.debian.org/debian stretch main" > /etc/apt/sources.list

# Install dependencies:
RUN apt-get update
RUN apt-get install -y libpng-dev

# Install PHP extensions:
RUN docker-php-ext-install mysqli
RUN docker-php-ext-install gd

# Use the default production configuration:
RUN mv "$PHP_INI_DIR/php.ini-production" "$PHP_INI_DIR/php.ini"

# Restart apache service:
RUN service apache2 restart

# Grant permissions on Apache directory:
RUN chmod -Rf 777 /var/www/html/
# ------------------------------------------------------------------------------------- #