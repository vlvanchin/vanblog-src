+++
title = "Tips on Webservice"
description = "This page show some of the most used commands in Webservice"
tags = [
    "webservice",
    "development",
]
date = "2020-07-02"
categories = [
    "Development",
    "webservice",
]
menu = "main"
author = "van"
+++

# jax-ws using soap and wsdl
# ----------------------------
```
> mkdir -p helloservice/endpoint/
> mkdir build
> javac -d build helloservice/endpoint/*java
> C:\dev\ides\eclipse\workspace\attachmentws>wsgen -d build -s build -cp c:\dev\ides\eclipse\workspace\attachmentws\build helloservice.endpoint.Hello
> java -cp  build helloservice.endpoint.Server
```

# This is to generated web service classes for the service and WSDL and XSD
```
C:\dev\ides\eclipse\workspace\FileAttachmentExample>wsgen -d bin -s bin -wsdl -cp c:\dev\ides\eclipse\workspace\FileAttachmentExample\bin com.company.jira.services.ws.attach.server.FileTransferImpl
```

# This is to generate web service classes for the client based on the WSDL from the localhost
```
wsimport -keep -p net.codejava.ws.binary.client http://localhost:9898/codejava/fileService?wsdl
```

