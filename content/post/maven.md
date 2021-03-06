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
2. generate-sources
3. process-sources
4. generate-resources
5. process-resources
6. compile
```

## Maven Archetypes
Here are some of the useful commands of Archetypes

### :Generate
The following command will create a Maven project com.my.app:my-first-app:1.0-SNAPSHOT application using the Generate maven goal., `archetype:generate`
```
mvn archetype:generate -DgroupId=com.my.app -DartifactId=my-first-app -DarchetypeArtifactId=maven-archetype-quickstart -DarchetypeVersion=1.4 -DinteractiveMode=false
or
mvn -B archetype:generate -DgroupId=com.my.app -DartifactId=my-first-app -DarchetypeArtifactId=maven-archetype-quickstart -DarchetypeVersion=1.4 -DinteractiveMode=false

```

the following command will create a maven project that is a site for the project
```
mvn archetype:generate \
  -DgroupId=com.my.app \
  -DartifactId=my-first-app-site \
  -DarchetypeGroupId=org.apache.maven.archetypes \
  -DarchetypeArtifactId=maven-archetype-site \
  -DinteractiveMode=false
```

the following command will create a maven web project
```
mvn archetype:generate \
    -DgroupId=com.my.app \
    -DartifactId=my-webapp \
    -DarchetypeGroupId=org.apache.maven.archetypes \
    -DarchetypeArtifactId=maven-archetype-webapp \
    -DinteractiveMode=false
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

---

# POM details
Here we will see some of the details of the POM.xml file

Here are the list of tag elements used within POM

`project` this is the top level element in all pom.xml files

`modelVersion` this indicates what version of the object model this POM is using.

`groupId` this indicates the unique identifier of the org/group that created this project.

`artifactId` this indicates the unique base name of the primary artifact being generated by this project.

`version` this indicates the version of the artifact generated by the project

`name` this indicates the display name used for the project

`url` this indicates where the project's site can be found

`properties` this element contains value placeholders accessible within the POM

`dependencies` this element's childern list all the dependencies used by this project

`build` this element handles things like declaring your project's directory structure and managing plugins

---


