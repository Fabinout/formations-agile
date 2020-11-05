FROM php:7.4-apache
WORKDIR "/var/www/html/"
VOLUME ["/var/www/html/"]

ENV APACHE_DOCUMENT_ROOT /var/www/html/test/web
RUN sed -ri -e 's!/var/www/html!${APACHE_DOCUMENT_ROOT}!g' /etc/apache2/sites-available/*.conf
RUN sed -ri -e 's!/var/www/!${APACHE_DOCUMENT_ROOT}!g' /etc/apache2/apache2.conf /etc/apache2/conf-available/*.conf


# BUILD :
# docker build -t php-test --no-cache=true .

# RUN :
# docker run -d -p 8080:80 --rm -v $PWD:/var/www/html  php-test