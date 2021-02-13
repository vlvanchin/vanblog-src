+++
title = "Maven"
description = "This page shows some basic commands of Maven Tool"
tags = [
    "Maven",
    "Mvn",
]
date = "2021-02-13"
categories = [
    "Maven",
    "Mvn",
]
menu = "main"
author = "van"
+++

# Maven Examples
This page shows some useful commands of Maven tool

## Maven Phases
Here are the list of Phases in the maven lifecycle 

> validate
> compile
> test
> package
> integration-test
> verify
> install
> deploy

other phases are
> clean
> site

Most of the phases have many steps or processes within., example: `package`
```
1. validate
1. generate-sources
1. process-sources
1. generate-resources
1. process-resources
1. compile
```

## Maven Archetypes
Here are some of the useful commands of Archetypes

### :Generate
The following command will create a Maven project com.my.app:my-first-app:1.0-SNAPSHOT application using the Generate maven goal., `archetype:generate`
```
mvn archetype:generate -DgroupId=com.my.app -DartifactId=my-first-app -DarchetypeArtifactId=maven-archetype-quickstart -DarchetypeVersion=1.4 -DinteractiveMode=false
```

## Maven Goals and Phases can be invoked in a sequence together
Here is an example to clean the project, copy the dependencies and package the project
```
mvn clean dependency:copy-dependencies package
```

### maven package
The following command will create the jar file into the target folder
```
mvn package
```

### execute the generated package
The following command will execute the jar file
```
java -cp target/my-first-app-1.0-SNAPSHOT.jar com.my.app.App
```



