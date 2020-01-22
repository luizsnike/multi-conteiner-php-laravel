FROM phpdockerio/php73-fpm:latest
WORKDIR "/application/site1"

# Fix debconf warnings upon build
ARG DEBIAN_FRONTEND=noninteractive

# Install selected extensions and other stuff
RUN apt-get update \
    && apt-get -y --no-install-recommends install php7.3-mysql php-soap php7.3-soap libxml2-dev php-redis php-mongodb libxml2-dev \
    && apt-get clean -y \
    && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* /usr/share/doc/*

# Install NodeJS e NPM
# RUN apt-get -y --no-install-recommends install  nodejs npm \

# Install git
# RUN apt-get update \
#    && apt-get -y install git \
#    && apt-get clean; rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* /usr/share/doc/*

# Install Depenpendecia Composer
# RUN composer install && composer update
