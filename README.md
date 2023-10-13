# Example project using Laravel and Docker

## Requirements
- [Docker](https://docs.docker.com/engine/install/) and [Docker Compose](https://docs.docker.com/compose/install/)
- [VSCode](https://code.visualstudio.com/download)
- VSCode extension: Dev Containers

## Setup
- Clone this repository.
~~~shell
git clone git@github.com:JefJrFigueiredo/laravel-docker.git
~~~
- Enter the repository
~~~shell
cd laravel-docker
~~~
- Create the .env file given by the author in the root of the project
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
