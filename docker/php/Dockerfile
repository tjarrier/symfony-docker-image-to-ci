FROM php:8.2.6-fpm-alpine

RUN apk update && apk add --no-cache git libzip-dev npm wget curl bash openssh libxslt-dev postgresql-dev nodejs npm
RUN docker-php-ext-install zip mysqli pdo pdo_mysql pdo_pgsql xsl
RUN npm install -g yarn

# Composer
RUN curl -sSk https://getcomposer.org/installer | php -- --disable-tls && mv composer.phar /usr/local/bin/composer

# Symfony CLI
RUN curl -1sLf 'https://dl.cloudsmith.io/public/symfony/stable/setup.alpine.sh' | bash && apk add symfony-cli

# Redis
RUN apk add --no-cache pcre-dev $PHPIZE_DEPS \
        && pecl install redis \
        && docker-php-ext-enable redis.so
