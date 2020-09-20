+++
title = "Docker Swarm"
description = "This page show some of the most used commands in Docker Swarm"
tags = [
    "docker",
    "swarm",
    "development",
]
date = "2020-04-03"
categories = [
    "Development",
    "docker",
    "swarm",
]
menu = "main"
author = "van"
+++

# Docker Swarm

### to initialize Swarm
```
$ docker swarm init
or 
$ docker swarm init --advertise-addr $(hostname -i)
```

### to join as a worker node
from the above init command the manager node is configured and there would be two commands listed, one to join as a worker node and other to join as another manager node.

```
$ docker swarm join --token <xxxxx-x-xxx...> <host>
```

### to show the list of nodes in action 
this will show the active nodes and the *Leader* node
```
$ docker node ls
```

### how to deploy a stack of docker services
// this accepts docker-compose format file for configurations
```
$ docker stack deploy
ex: $ docker stack deploy --compose-file docker-stack.yml vote
```
// how to verify the stack has been deployed.
```
$ docker stack ls
```

// to get details of each service within the stack
```
$ docker stack services vote
```
The above command's output might be as follows:

```
ID                  NAME                      MODE                REPLICAS            IMAGE                                          PORTS
050tqzdi1f5y        voting_stack_redis        replicated          1/1                 redis:alpine
bw8wb1gk81vh        voting_stack_db           replicated          1/1                 postgres:9.4
e43khvw4fqp6        voting_stack_result       replicated          1/1                 dockersamples/examplevotingapp_result:before   *:5001->80/tcp
klh2z7ogg1pj        voting_stack_worker       replicated          1/1                 dockersamples/examplevotingapp_worker:latest
v396yxpzss2x        voting_stack_vote         replicated          2/2                 dockersamples/examplevotingapp_vote:before     *:5000->80/tcp
vg8wvp7dmh35        voting_stack_visualizer   replicated          1/1                 dockersamples/visualizer:stable                *:8080->8080/tcp
```

### to list all the tasks of a service that has many replicas
```
$ docker service ps voting_stack_vote
```
The output of this above command
```
ID                  NAME                  IMAGE                                        NODE                DESIRED STATE       CURRENT STATEERROR               PORTS
vvyl6ftqgq19        voting_stack_vote.1   dockersamples/examplevotingapp_vote:before   node1               Running             Running 17 minutes ago
pk1m9lrrpc67        voting_stack_vote.2   dockersamples/examplevotingapp_vote:before   node2               Running             Running 17 minutes ago
```

### Test Run
http://localhost:5000
otherwise: http://127.0.0.1:5000

if you are trying this in AWS or Azure or any cloud, then try to port forward the request, using the following
```
$ ssh -L <port>:localhost:<port> <ssh-user>@<CLOUD_INSTANCE_IP_ADDRESS>
```

### App Customization
Change in the docker-stack.yml file to Java and .Net instead of Cats and Dogs and from before to after tags.

Redeploy the services:
  here the redeploy is same as the deployment. so we run the deploy command once again
```
  $ docker stack deploy --compose-file docker-stack.yml vote
```

// to increase the number of replicas of the voting_stack_vote service
```
$ docker service scale voting_stack_vote=5
```

### Remove the stack
```
$ docker stack rm <stack_name>
ex: $ docker stack rm vote
```

