FROM php:8.1.1-fpm-alpine

RUN apk update && apk add --no-cache git libzip-dev npm wget curl bash openssh libxslt-dev
RUN docker-php-ext-install zip mysqli pdo pdo_mysql xsl
RUN npm install -g yarn

# Composer
RUN curl -sSk https://getcomposer.org/installer | php -- --disable-tls && mv composer.phar /usr/local/bin/composer

# Symfony CLI
RUN wget https://get.symfony.com/cli/installer -O - | bash && mv /root/.symfony/bin/symfony /usr/local/bin/symfony