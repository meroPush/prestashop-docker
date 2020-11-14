FROM prestashop/prestashop:1.6.1.6

# To run files with the same group as your primary user
RUN groupmod -g 1000 www-data && \
    usermod -u 1000 -g 1000 www-data && \
    chown -R www-data:www-data /tmp /var/www/html

# Install xdebug
RUN pecl install xdebug-2.5.5 && docker-php-ext-enable xdebug.so

# Install memcached
RUN apt-get update && \
    apt-get install -y libz-dev libmemcached-dev && \
    pecl install memcached-2.2.0 && \
    docker-php-ext-enable memcached.so
