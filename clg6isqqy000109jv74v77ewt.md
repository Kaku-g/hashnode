---
title: "Dockerfiles for diffferent tech stacks"
seoTitle: "Dockerize and run your app with the blink of a speed"
seoDescription: "Dockerize and run your app with the blink of a speed"
datePublished: Fri Apr 07 2023 12:25:34 GMT+0000 (Coordinated Universal Time)
cuid: clg6isqqy000109jv74v77ewt
slug: dockerfiles-for-diffferent-tech-stacks
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/jOqJbvo1P9g/upload/9497284e134be4917459cd31860940e0.jpeg
tags: docker, apis, rest-api, yaml, containers

---

Dockerize your application with the blink of a speed using the following template for different tech stacks.

PS- Assume and modify the appropriate version in the file, according to your requirements.

* Nodejs REST API which listens on port 8080
    

```yaml
FROM node:14
# Change working directory
WORKDIR /app
#copy package.json to image
COPY package.json .
# installing all the dependencies
RUN npm install
# copying all the source code to the image
COPY . .
#exposing port 8080 of the application
EXPOSE 8080
#running the script to start the server
CMD ["npm","start"]
```

* Python - Running a Flask application that listens on port 5000:
    

```yaml
FROM python:3.7-stretch

# Install modules
RUN pip install Flask

# Needed by the Flask module
ENV FLASK_APP=server.py

# Copy source files into the image
COPY templates ./templates
COPY server.py .

EXPOSE 5000

CMD ["flask", "run", "--host=0.0.0.0"]
```

* Java Rest API
    

```yaml
# Use an image with the SDK for compilation
FROM openjdk:8-jdk-alpine AS builder
WORKDIR /out
# Get the source code inside the image 
COPY *.java .
# Compile source code
RUN javac Hello.java

# Create a lightweight image 
FROM openjdk:8-jre-alpine
# Copy compiled artifacts from previous image
COPY --from=builder /out/*.class .
CMD ["java", "Hello"]
```

* PHP Rest API
    

```yaml
FROM php:7.0-apache

# Install Apache module
RUN a2enmod rewrite

COPY . /var/www/html/
```

* .Net Core Rest API
    

```yaml

# Use an image with the SDK for compilation
FROM microsoft/dotnet:2.2-sdk AS builder
WORKDIR /app

# Get the build file
COPY *.csproj  .
# Optional. Run this first so that it is cached
RUN dotnet restore

# Get the source code inside the image 
COPY . .
RUN dotnet publish --output /out/ --configuration Release

# Create a lightweight image
FROM microsoft/dotnet:2.2-aspnetcore-runtime-alpine
WORKDIR /app
# Copy compiled artifacts from previous image
COPY --from=builder /out .
EXPOSE 80
ENTRYPOINT ["dotnet", "aspnet-core.dll"]
```

Also, check out this latest Chrome extension to manage your tabs!

[Get extension](https://chrome.google.com/webstore/detail/tabster/epjkekcpjdffopichkinfjabbakeamhe?hl=en&authuser=0)