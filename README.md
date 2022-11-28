# Nginx PHP-FPM Docker image

> 🐳 Full Docker image for Nginx PHP-FPM container created to run any php based applications.

- [Github](https://github.com/philharmonie/nginx-php-fpm)

## Specifications:

* PHP 8.2 / 8.1 / 8.0 / 7.4 / 7.2
* Composer
* OpenSSL PHP Extension
* XML PHP Extension
* PDO PHP Extension
* Mbstring PHP Extension
* PCNTL PHP Extension
* ZIP PHP Extension
* GD PHP Extension
* BCMath PHP Extension
* Memcached
* Supervisord
* Nodejs
* NPM

## Simple docker-compose usage:

```yml
version: '3'
services:
    app:
        image: philharmonie/nginx-php-fpm:latest
        container_name: my-app
        restart: unless-stopped      
        volumes:
        #Project root
            - ./:/var/www/html
        ports:
           - "80:80"
        networks:
            - default #if you're using networks between containers


## Advanced Nignx-php-fpm:
### docker-compose.yml
```yml
version: '3'
services:
    app:
        image: philharmonie/nginx-php-fpm
        container_name: nginx-fpm
        restart: unless-stopped 
        ports:
           - "80:80"    
        volumes:
        #Project root
            - ./:/var/www/html
            - ~/.ssh:/root/.ssh # If you use private CVS
             #./php.ini:/usr/local/etc/php/conf.d/php.ini # Optional, your custom php init file
        environment:
           - APP_ENV=development # Optional, or production
           #- CLIENT_MAX_BODY_SIZE=20M # Optional
           #- DOMAIN=example.com # Optional
           - DOCUMENT_ROOT=/var/www/html #Optional
 
```

## Docker run
```sh
 docker-compose up -d

```
## Nginx custom config:
### Enable custom nginx config files
> /var/www/html/conf/nginx/nginx.conf

> /var/www/html/conf/nginx/nginx-site.conf

## Supervisord
### Add more supervisor process in
> /var/www/html/conf/worker/supervisor.conf


> P.S. please give a star if you like it :wink:


