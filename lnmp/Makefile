pull:
	docker pull nginx:1.10.1
	docker pull php:5.6-fpm
	docker pull mysql:5.6
	docker pull redis:3.0
	

dl:
	wget https://pecl.php.net/get/redis-2.2.7.tgz -O php/redis.tgz
	wget https://pecl.php.net/get/xdebug-2.3.2.tgz -O php/xdebug.tgz
	wget https://pecl.php.net/get/xhprof-0.9.4.tgz -O php/xhprof.tgz
	wget https://getcomposer.org/composer.phar -O php/composer.phar

build:
	make build-nginx
	make build-mysql
	make build-php

build-nginx:
	docker build -t data/nginx ./nginx

run-nginx:
	docker run -i -d -p 80:80 -v ~/data:/data -t data/nginx

in-nginx:
	docker run -i -p 80:80 -v ~/data:/data -t data/nginx /bin/bash

build-php:
	docker build -t data/php ./php

run-php:
	docker run -i -d -p 9000:9000 -v ~/data:/data -t data/php

in-php:
	docker run -i -p 9000:9000 -v ~/data:/data -t data/php /bin/bash

build-mysql:
	docker build -t data/mysql ./mysql

run-mysql:
	docker run -i -d -p 3306:3306 -v ~/data/data/mysql:/var/lib/mysql -e MYSQL_ROOT_PASSWORD=root -t data/mysql

in-mysql:
	docker run -i -p 3306:3306  -v ~/data/data/mysql:/var/lib/mysql -e MYSQL_ROOT_PASSWORD=root -t data/mysql /bin/bash
	
clean:
	docker rmi -f $(shell docker images | grep "<none>" | awk "{print \$3}")