+++
title = "docker machine"
description = "This page shows some basic commands used in Docker-Machine"
tags = [
    "machine",
]
date = "2021-04-13"
categories = [
    "machine",
]
menu = "main"
author = "van"
+++

# Docker-machine

This section shows some of the useful commands for Docker-machine. ... it is a good practice to do run docker machines from any folder.

## Docker-machine Installation

Download the `docker-machine` from the $base URL, extract and change mode for execution

```
$ curl -L $base/docker-machine-$(uname -s)-$(uname -m) > /tmp/docker-machine

$ sudo mv /tmp/docker-machine /usr/local/bin/docker-machine

$ chmod +x /usr/local/bin/docker-machine
```

Test if the tool is installed, try the following `$ docker-machine version`. To view all the option try `$ docker-machine -h`.

## Docker-machine usefull commands

To view all the docker-machines in the host machine 

```
$ docker-machine ls
```

In order to create a docker-machine, where the machine name is 'default', try the following
```
$ docker-machine create --driver virtualbox default
``` 
here we have provided the 'virtualbox' driver to be as virtualization.

To view the environment of the newly created docker-machine 
```
$ docker-machine env default
```

To execute the docker commands in the newly created docker-machine is as follows. This maps the default machine
```
$ eval $(docker-machine env default)
```

hereafter any docker commands run will be executed in the default docker-machine, the prompt in the terminal will show the name of the docker-machine

Commands to 'start' or 'stop' the docker-machine eg., default

```
$ docker-machine start default

$ docker-machine stop default
```

### docker commands issued to the default machine

To find the IP address of the default machine
```
$ docker-machine ip default
```

To view or browse default machine at port 8080
```
$ curl $(docker-machine ip default):8080
```

To unmap the default docker-machine 
```
$ eval $(docker-machine env -u)
```

