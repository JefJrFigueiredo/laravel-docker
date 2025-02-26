# Example project using Laravel and Docker

## Requirements
- [Docker](https://docs.docker.com/engine/install/) and [Docker Compose](https://docs.docker.com/compose/install/)
- [VSCode](https://code.visualstudio.com/download)
- VSCode extension: Dev Containers
- If needed, use the convenience scripts of [this repository](https://github.com/JefJrFigueiredo/sh-for-dev-env/tree/main) to configure the Github SSH and install Docker and Docker Compose in a Linux or WSL2

## Setup
- Clone this repository
~~~shell
git clone git@github.com:JefJrFigueiredo/laravel-docker.git
~~~
- Enter the repository
~~~shell
cd laravel-docker
~~~
- Create the .env file
~~~shell
cp .env.example .env
~~~
- Use the following [command](https://laravel.com/docs/10.x/sail#installing-composer-dependencies-for-existing-projects) for installing dependencies:
~~~shell
docker run --rm \
    -u "$(id -u):$(id -g)" \
    -v "$(pwd):/var/www/html" \
    -w /var/www/html \
    laravelsail/php84-composer:latest \
    bash -c "composer install --ignore-platform-reqs && php artisan sail:install"
~~~
- Generate the app_key
~~~shell
./vendor/bin/sail artisan key:generate
~~~
- Open this folder in VSCode and reopen in container.
- After container is built, run 'localhost' in browser to see Laravel welcome page.
