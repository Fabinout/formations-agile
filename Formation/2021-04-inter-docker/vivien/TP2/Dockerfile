FROM webdevops/php-nginx
WORKDIR /var/www/html
RUN rm *
RUN cp conf/sites-enabled/* /etc/nginx/sites-enabled/
RUN composer create-project --prefer-dist laravel/laravel .