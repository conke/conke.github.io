---
layout: post
title: "Web Server Best Practice"
date: "2017-05-05 22:34:06 +0800"
---

<!-- TOC -->

- [1. HTTP Server Setup](#1-http-server-setup)
- [2. HTTP Server v1](#2-http-server-v1)
- [3. HTTP Server v1](#3-http-server-v1)
- [4. HTTP Server v1](#4-http-server-v1)
- [5. HTTP Server v4](#5-http-server-v4)
- [6. App Server Setup](#6-app-server-setup)
- [7. App Server + Demo v1](#7-app-server-demo-v1)
- [8. App Server + Demo v2](#8-app-server-demo-v2)
- [9. App Server + Demo v3](#9-app-server-demo-v3)
- [10. Devel Env Setup, Demo v1](#10-devel-env-setup-demo-v1)
- [11. Demo v2](#11-demo-v2)
- [12. Demo v2](#12-demo-v2)
- [13. Demo V3](#13-demo-v3)
- [14. App](#14-app)
- [15. App Deployment ready](#15-app-deployment-ready)
- [16. Database Setup](#16-database-setup)
- [17. Lang + DB](#17-lang-db)
- [18. System Integration](#18-system-integration)

<!-- /TOC -->
![](/res/web-server-best-practice/best-practice.png)


## 1. Overview

1. uWSGI (almost all)
    1. Python
    2. Lua
    3. Perl
    4. Ruby
    5. Erlang
    6. PHP
    7. Go
    8. Java
    9. ASP
    10. V8
2. FastCGI (almost all)
3. Passenger
4. Unicorn
    11. Ruby
5. Gunicorn
    12. Python
6. mod_wsgi
    13. python


1. PHP
    1. mod_php
    2. php-fpm
    3. FastCGI
2. Python
    4. mod_wsgi
    5. uWSGI
    6. Gunicorn
    7. FastCGI
3. Ruby
    8. passenger
    9. Unicorn
    10. FastCGI
4. Java
    11. Tomcat
    12. JBoss
    13. FastCGI
5. Go
    14. FastCGI


需要考虑一下几个方面：

* stability (稳定性)
* performance (性能)
* scalability (可扩展性)



## 2. Installation

### 2.1. mod_wsgi

[django官方文档](https://modwsgi.readthedocs.io/en/develop/user-guides/virtual-environments.html)中有这么一段话：

_When using a Python virtual environment with mod_wsgi, it is very important that it has been created using the same Python installation that mod_wsgi was originally compiled for. It is not possible to use a Python virtual environment to force mod_wsgi to use a different Python version, or even a different Python installation._

所以需要根据当前的python版本安装对应的mod_wsgi:


```bash
pip install mod_wsgi
```

<!--
CentOS6:

```bash
sudo yum install -y python35u-mod_wsgi
```

Ubuntu:

```bash
sudo apt install libapache2-mod-wsgi
```

FreeBSD:

```bash
sudo pkg install ap22-mod_wsgi2
```
-->

try to launch:

```bash
mod_wsgi-express start-server
```

#### 2.1.1. uWSGI

```bash
pip install uwsgi
```


#### 2.1.1. uWSGI

```bash
pip install gunicorn
```

## 3. 运行demo1——极简demo

### 3.1. Python版

update demo1.py:

```python
import time
import sys, platform

def application(env, start_response):
    start_response('200 OK', [('Content-Type','text/html')])

    localtime = time.asctime( time.localtime(time.time()) )
    pyver = sys.executable + ': ' + platform.python_version()
    info = "%s<br/>%s" % (localtime, pyver)
    return [info.encode()] # py3
```

#### 3.1.2. mod_wsgi

```bash
mod_wsgi-express start-server demo1.py
```

#### 3.1.3. uWSGI

```bash
uwsgi --http :8000 --wsgi-file demo1.py
```

#### gunicorn

```bash
gunicorn -w 4 demo1:application
```

### 3.2. demo1 v2


### 3.3. run demo1 v2

demo1

```bash
mod_wsgi-express start-server demo1/wsgi.py
```


might fail if mod_wsgi not installed in current env (installed globally), fix with:

```bash
mod_wsgi-express start-server demo/wsgi.py --python-path /opt/envs/py35-django/lib/python3.5/site-packages/
```


## 4. 整合HTTP Server

### 4.1. Apache

#### 4.1.1. Apache + mod_wsgi

install mod_wsgi to Apache:

```bash
mod_wsgi-express install-module > mod_wsgi.conf
sudo cp -v mod_wsgi.conf /etc/httpd/conf.d/
```

copy code:

```bash
sudo mkdir /var/www/$DN
sudo cp -r demo1 /var/www/$DN/demo
```

create /etc/httpd/conf.d/$DN.conf:

```apache
WSGIPythonPath "/var/www/x.lamp.io/"

<VirtualHost *:80>


    WSGIScriptAlias / /var/www/x.lamp.io/demo/wsgi.py

    <Directory /var/www/x.lamp.io/demo>
    Order allow,deny
    Allow from all
    </Directory>

</VirtualHost>
```

### 4.2. Nginx


<!--
https://www.peterbe.com/plog/fcgi-vs-gunicorn-vs-uwsgi

https://blog.layershift.com/which-php-mode-apache-vs-cgi-vs-fastcgi/

http://stackoverflow.com/questions/10036238/deploying-go-web-applications-with-apache
-->


## 1. HTTP Server Setup


## 2. 创建demo站点（前端部分）

```bash
mkdir $DN
mkdir $DN/static
```

edit $DN/static/index.html:

```html
<h1 align='center'>Welcome to x.lamp.io!</h1>
<marquee>static page</marquee>
```

(TODO: add http server info？)


### 6.2. DNS与Virtual Host（虚拟主机）

#### 6.2.1. 关于DNS

```bash
DN='x.lamp.io'
```

```bash
sudo su -c "echo '127.0.0.1   $DN' >> /etc/hosts"  # >> !
```

test:

```bash
ping $DN
```

#### 6.2.2. Apache Virtual Host

create /etc/httpd/conf.d/$DN.conf:

```apache
<VirtualHost *:80>

    ServerName x.lamp.io
    ServerAdmin webmaster@x.lamp.io

    DocumentRoot /var/www/x.lamp.io/static/

    <Directory /var/www/x.lamp.io/static>
    Order allow,deny
    Allow from all
    </Directory>

</VirtualHost>
```

```bash
sudo service httpd restart
```


change the 'DocumentRoot' line to

```apache
Alias /static/ /var/www/x.lamp.io/static/
```

pls note the 2 end '/'s!

#### 6.2.3. Nginx Virtual Host

#### 6.2.4. Verification

```bash
curl http://$DN
w3m http://$DN # 'q' to quit
firefox http://$DN
# others
```

for further verification, create DN1, say 'y.lamp.io', and repeat the previous steps.

# LAMP: Apache and Nginx

## Installation

### Install Apache

on RHEL/CentOS/Fedora:
```
$ sudo dnf install -y httpd
$ sudo systemctl enable httpd
$ sudo systemctl start httpd
```

on Ubuntu/Debian:
```
$ sudo apt install -y apache2
```

on Arch Linux:
```
$ sudo pacman install apache
```

on macOS: (Apache is built in, so we just need to start the service)
```
$ sudo apachectl start
```

### Install Nginx (FIXME)

on RHEL/CentOS/Fedora:
```
$ sudo dnf install -y nginx
$ sudo systemctl enable nginx
$ sudo systemctl start nginx
```

on Ubuntu/Debian:
```
$ sudo apt install -y nginx
```

on Arch Linux:
```
$ sudo pacman install nginx
```

on macOS: (Apache is built in, so we just need to start the service)
```
$
```

### Firewall

### Make sure Apache/Nginx works
```
(run netstat if necessary)
$ curl http://localhost (from local)
$ curl http://ip (from remote)
```

## Configuration

### Apache

/$

Alias and DocumentRoot

## module development

```bash
apxs -g -n demo
```

## What's Next

## 2. HTTP Server v1

## 3. HTTP Server v1

## 4. HTTP Server v1

## 5. HTTP Server v4

## 6. App Server Setup

## 7. App Server + Demo v1

## 8. App Server + Demo v2

## 9. App Server + Demo v3

## 10. Devel Env Setup, Demo v1

## 11. Demo v2

## 12. Demo v2

## 13. Demo V3

## 14. App

## 15. App Deployment ready

## 16. Database Setup

## 17. Lang + DB

## 18. System Integration

### 5.1. 版本选择

#### 5.1.1. Python

考虑一：基本工具（pip & venv）的支持

version | source | pip | 语言内建venv | 结论 = pip \| venv
--------|--------|-----|-------------|----
2.6 | Base | T, [但已经deprecated](/programming/build) | F | F
2.7 | IUS | T | F | T
3.4 | EPEL | F | T, 但"--without-pip" | 需要手动get-pip
3.4 | IUS | T | T | T
3.5 | IUS | T | T | T
3.6 | IUS | F | T | T

看来CentOS6(Base+EPEL)对Python的支持并不好。

考虑二：对uWSGI和mod_wsgi的支持

version | source | uWSGI | mod_wsgi | 结论 = uWSGI & mod_wsgi
--------|--------|-------|----------|-----
2.7 | IUS | T | T | T
3.4 | EPEL | F | F | F
3.4 | IUS | T | F | F
3.5 | IUS | T | T | T
3.6 | IUS | F | F | F

——花了一个上午，突然发现表一（考虑一）基本是多余的！:sob:
<!--不过没有删除仍保留着，是考虑到这样的工作方式和思路可能对你有参考和帮助。-->

剩下2.7和3.5
