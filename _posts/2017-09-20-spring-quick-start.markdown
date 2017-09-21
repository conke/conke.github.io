---
layout: post
title: "Spring Quick Start"
date: "2017-09-20 20:46:52 -0700"
---

# Install Spring Boot CLI

```bash
sdk install springboot
spring --version
```

# Create Spring Projects

## Create a normal spring project

### Spring with maven

```bash
sping init demo1
cd demo1m
mvn spring-boot:run
```

check directory tree and pom.xml

```bash
tree
vi pom.xml
```

### Spring with gradle

```bash
sping init --build=gradle demo1
cd demo1
gradle bootRun
```

check directory tree and build.gradle

## Other ways to run spring-boot project

way 1:

```bash
mvn package
java -jar target/demo1-xxx.jar
```

way 2:

add to pom.xml:

```xml
 <executable>true</executable>
```

and
```bash
./target/demo1-x.tar
```

## Create a SpringMVC project

### Create/Init a project
```bash
spring init -d=web demo2
tree
```

### Run

```bash
cd demo2
mvn spring-boot:run
```

open web browser

```bash
firefox localhost:8080
```

### Add code
