FROM prestashop/prestashop:1.7.6.8

# To run files with the same group as your primary user
RUN groupmod -g 1000 www-data && \
    usermod -u 1000 -g 1000 www-data && \
    chown -R www-data:www-data /tmp /var/www/html

# Install xdebug
RUN pecl install xdebug-2.9.8 && docker-php-ext-enable xdebug

# Install memcached
RUN apt-get update && \
    apt-get install -y libz-dev libmemcached-dev && \
    pecl install memcached-3.1.5 && \
    echo extension=memcached.so >> /usr/local/etc/php/conf.d/memcached.ini
