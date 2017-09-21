---
layout: post
title: "Spring Quick Start"
date: "2017-09-20 20:46:52 -0700"
---

<!-- TOC -->

- [1. Install Spring Boot CLI](#1-install-spring-boot-cli)
- [2. Create Spring Projects](#2-create-spring-projects)
    - [2.1. Create a normal spring project](#21-create-a-normal-spring-project)
        - [2.1.1. Spring with maven](#211-spring-with-maven)
        - [2.1.2. Spring with gradle](#212-spring-with-gradle)
    - [2.2. Other ways to run spring-boot project](#22-other-ways-to-run-spring-boot-project)
    - [2.3. Create a SpringMVC project](#23-create-a-springmvc-project)
        - [2.3.1. Create/Init a project](#231-createinit-a-project)
        - [2.3.2. Run](#232-run)
        - [2.3.3. Add code](#233-add-code)

<!-- /TOC -->

# 1. Install Spring Boot CLI

```bash
sdk install springboot
spring --version
```

# 2. Create Spring Projects

## 2.1. Create a normal spring project

### 2.1.1. Spring with maven

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

### 2.1.2. Spring with gradle

```bash
sping init --build=gradle demo1
cd demo1
gradle bootRun
```

check directory tree and build.gradle

## 2.2. Other ways to run spring-boot project

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

## 2.3. Create a SpringMVC project

### 2.3.1. Create/Init a project
```bash
spring init -d=web demo2
tree
```

### 2.3.2. Run

```bash
cd demo2
mvn spring-boot:run
```

open web browser

```bash
firefox localhost:8080
```

### 2.3.3. Add code
