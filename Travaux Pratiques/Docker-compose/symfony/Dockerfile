FROM composer AS composer
COPY . /app
RUN rm -rf vendor && composer install --no-dev
RUN rm -rf nginx

# Image based on https://hub.docker.com/r/trafex/alpine-nginx-php7
FROM trafex/alpine-nginx-php7
USER root
RUN apk --no-cache add php7-pdo php7-pdo_mysql php7-tokenizer
COPY nginx/symfony.conf /etc/nginx/nginx.conf

USER nobody

RUN mkdir -p /var/www/html/symfony
RUN mkdir -p /var/log/nginx/symfony

WORKDIR /var/www/html/symfony
COPY --from=composer --chown=nobody /app /var/www/html/symfony
