# Install composer
RUN php -r "copy('https://raw.githubusercontent.com/composer/getcomposer.org/master/web/installer', 'composer-setup.php');" && \
    php composer-setup.php && \
    php -r "unlink('composer-setup.php');" && \
    mv composer.phar /usr/local/bin/composer

RUN (pecl install xdebug || pecl install xdebug-2.5.5) && docker-php-ext-enable xdebug

EXPOSE 9000
HEALTHCHECK CMD /bin/nc -z 127.0.0.1 9000