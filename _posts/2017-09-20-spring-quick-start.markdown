---
layout: post
title: "Spring Quick Sjart"
date: "2017-09-20 20:46:52 -0700"
---

<!-- TOC -->

- [1. Install Spring Boot CLI](#1-install-spring-boot-cli)
- [2. Create Spring Projects](#2-create-spring-projects)
    - [2.1. Create a normal spring project](#21-create-a-normal-spring-project)
        - [2.1.1. Spring with maven](#211-spring-with-maven)
        - [2.1.2. Spring with gradle](#212-spring-with-gradle)
- [3. Package and make executable](#3-package-and-make-executable)
    - [3.1. Maven](#31-maven)
        - [3.1.1. package](#311-package)
        - [3.1.2. make executable](#312-make-executable)
    - [3.2. Gradle](#32-gradle)
        - [3.2.1. package](#321-package)
        - [3.2.2. make executable](#322-make-executable)
- [4. Create a SpringMVC project](#4-create-a-springmvc-project)
    - [4.1. Create/Init a project](#41-createinit-a-project)
    - [4.2. Run](#42-run)
    - [4.3. Add code](#43-add-code)

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
cd demo1
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

# 3. Package and make executable

## 3.1. Maven

### 3.1.1. package

```bash
mvn package
java -jar target/demo1-xxx.jar
```

### 3.1.2. make executable

add to pom.xml:

```xml
<plugin>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-maven-plugin</artifactId>
    <!-- begin -->
    <configuration>
        <executable>true</executable>
    </configuration>
    <!-- end -->
</plugin>
```

and
```bash
mvn package
ls -l target
./target/demo1-x.jar
```

## 3.2. Gradle

### 3.2.1. package

```bash
gradle build
ls -l build
java -jar build/demo1-xxx.jar
```

### 3.2.2. make executable

add to build.gradle:

```groovy
springBoot {
    executable = true
}
```

and
```bash
gradle build
ls -l build
build/demo1-x.jar
```

# 4. Create a SpringMVC project

## 4.1. Create/Init a project
```bash
spring init -d=web demo2
tree
```

## 4.2. Run

```bash
cd demo2
mvn spring-boot:run
```

open web browser

```bash
firefox localhost:8080
```

## 4.3. Add code
