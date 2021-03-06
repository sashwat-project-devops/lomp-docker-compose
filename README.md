# LOMP (Linux-OpenLiteSpeed-MySQL-PHP) Docker Compose

## Introduction

This repository can be used to host LOMP (Linux, OpenLiteSpeed, Mariadb, PHP) server using docker compose. The docker images used for building LAMP stack are:-

1. Web server - litespeedtech/openlitespeed:1.6.9-lsphp74
2. API server - python:3.8.2
3. Database - mariadb:10.5.1-bionic
4. PHPMyAdmin - phpmyadmin/phpmyadmin

## Instructions

1. The default configuration is saved as `sample_env`. Copy contents from `sample_env` to `.env`.

   ```bash
   cp sample_env .env
   ```

2. Make necessary changes to `.env` file.
3. Build docker-compose image using the following command.

   ```bash
   docker-compose build --no-cache
   ```

4. Run docker-compose using the following command.

   ```bash
   docker-compose up -d
   ```

5. To shut down docker-compose container, using the following command.

   ```bash
   docker-compose down
   ```

## Architecture

![lamp-architecture](docs/architecture.png)

## Folder Structure

```
lomp-docker-compose
 ┣ bin
 ┃ ┣ apiserver
 ┃ ┃ ┣ code
 ┃ ┃ ┃ ┣ app.py
 ┃ ┃ ┃ ┗ requirements.txt
 ┃ ┃ ┗ Dockerfile
 ┃ ┣ mariadb
 ┃ ┃ ┗ Dockerfile
 ┃ ┣ phpmyadmin
 ┃ ┃ ┗ Dockerfile
 ┃ ┗ webserver
 ┃ ┃ ┣ Dockerfile
 ┃ ┃ ┗ index.php
 ┣ config
 ┃ ┣ openlitespeed-config
 ┃ ┃ ┗ httpd_config.conf
 ┃ ┣ openlitespeed-docker
 ┃ ┃ ┗ docker.conf
 ┃ ┣ openlitespeed-vhosts
 ┃ ┃ ┗ vhconf.conf
 ┃ ┗ php
 ┃ ┃ ┗ php.ini
 ┣ data
 ┃ ┗ .gitkeep
 ┣ docs
 ┃ ┣ architecture.drawio
 ┃ ┗ architecture.png
 ┣ logs
 ┃ ┗ openlitespeed
 ┃ ┃ ┗ .gitkeep
 ┣ .gitignore
 ┣ LICENSE
 ┣ README.md
 ┣ docker-compose.yaml
 ┗ sample_env
```

## Contributors

1. Sashwat K <sashwat0001@gmail.com>
