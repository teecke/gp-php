# Generic Platform - PHP Web Application

## Overview

Docker image and docker-compose sample configuration to bring up a PHP web application product to the Teecke [Docker Generic Platform (GP)](https://github.com/teecke/docker-generic-platform).

## Configuration

The product is formed by one container:

- **webapp**: based on [php:7.3.9-apache-buster](https://hub.docker.com/_/php?tab=tags&page=1&name=7.3.9-apache-buster) docker image.

## Operation

1. Use the `docker-compose.yml.sample` file as your docker-compose configuration file.

2. Create a docker network called "platform_services" before start the services with `docker network create platform_services`.

3. Create a directory called `webapp` and place your web application files within.

4. Start with `docker-compose up -d`.

5. Open a browser in the url <http://localhost:8080> to view your application running.

6. Manage backups of your files:

   1. Make a backup executing `docker-compose exec webapp backup`.
   2. Find the current backup within the `/var/backups/gp/webapp/` of the container.
   3. Extract the current backup executing `docker cp $(docker-compose ps -q webapp):/var/backups/gp gp`.

7. Stop the platform with `docker-compose stop`.

You can use this docker piece with the [Docker Generic Platform](https://github.com/teecke/docker-generic-platform) project.

## Known issues

None known
