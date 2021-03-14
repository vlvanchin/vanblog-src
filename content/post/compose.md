+++
title = "docker compose"
description = "This page shows some basic commands used in Docker-Compose"
tags = [
    "compose",
]
date = "2021-03-14"
categories = [
    "compose",
]
menu = "main"
author = "van"
+++

# Docker-compose

This section shows some of the useful commands for Docker-compose. ... it is a good practice to do compose stuff from a independent folder

## installation of docker-compose 

download and house the app /usr/local/bin

```
$ udo curl -L "https://github.com/docker/compose/releases/download/1.28.4/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
```

change the mode of the docker-compose to executable
```
chmod +x /usr/local/bin/docker-compose
```

* check the version of docker-compose using `docker-compose version`

## Steps to try docker-compose 

* create an arbitary folder say *docker-demo* and cd to it, it is the project folder

* create an app folder and write an index.html file with some static contents

* create an docker-compose.yml in the project folder
```
/docker-demo
|
|--app
|    |
|    |--index.html
|
|--docker-compose.yml    
```

* content of the docker-compose.yml is as follows

this file uses 3.7 version of the compose syntax, the configuration of services is done below having one *web* service that uses the image of *nginx:alpine* as a reverse proxy. The port *8000* is used from the host system which maps to the port *80* of the container. The volume for the container is mapped from *app* folder of host to */usr/share/nginx/html* in the container

```
version: '3.7'
services:
  web:
    image: nginx:alpine
    ports:
      - "8000:80"
    volumes:
      - ./app:/usr/share/nginx/html
```

## Running docker-compose

* to test this from the project folder run the following command

```
$ docker-compose up -d
```

* to view the status of the all the containers used in the app

```
$ docker-compose ps
```

## other useful commands in docker-compose

* to view the logs of the services in the application

```
$ docker-compose logs
```

* to pause the application

```
$ docker-compose pause
```

* to unpause the application

```
$ docker-compose unpause
```

* to stop the service, this stops all the services container executions

```
$ docker-compose stop
```

* to start the services

```
$ docker-compose start
```

* to down all the services, this terminates that containers and removes the network but not the volumes

```
$ docker-compose down
```

* to list all the images

```
$ docker-compose images
```

