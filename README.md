# Example Laravel project

## Requirements
- Docker
- VSCode
- VSCode extension: Dev Containers

## Setup
- Clone this repository.
- Set the .env file given by the author
- Use the following [command](https://laravel.com/docs/10.x/sail#installing-composer-dependencies-for-existing-projects) for installing dependencies:
~~~shell
docker run --rm \
    -u "$(id -u):$(id -g)" \
    -v "$(pwd):/var/www/html" \
    -w /var/www/html \
    laravelsail/php82-composer:latest \
    composer install --ignore-platform-reqs
~~~
- Open this folder in VSCode and reopen in container.
- After container is built, run 'localhost' in browser to see Laravel welcome page.