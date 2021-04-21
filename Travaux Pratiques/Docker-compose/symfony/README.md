#### Build a image ready to be deployed
Build an image based on alpine with nginx, php-fpm and required php dependencies.
Nginx server is listening by default on 8080.

	docker build -t symfony-app .

#### Test the app

	docker-compose up -d --build
	docker-compose exec symfony-app php bin/console doctrine:fixtures:load

#### Install a new package from composer
Start a container with composer and install dependency

    docker-compose run composer require symfony/flex
