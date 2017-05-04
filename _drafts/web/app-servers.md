[Home](/)
<br/>

# App Servers

Features:
* covers all OS and distributions/languages/
* frameworks and databases
* step by step, double check

<!-- TOC -->

- [1. Overview](#1-overview)
- [2. Installation](#2-installation)
    - [2.1. mod_wsgi](#21-mod_wsgi)
        - [2.1.1. uWSGI](#211-uwsgi)
        - [2.1.1. uWSGI](#211-uwsgi-1)
- [3. 运行demo1——极简demo](#3-运行demo1极简demo)
    - [3.1. Python版](#31-python版)
        - [3.1.2. mod_wsgi](#312-mod_wsgi)
        - [3.1.3. uWSGI](#313-uwsgi)
        - [gunicorn](#gunicorn)
    - [3.2. demo1 v2](#32-demo1-v2)
    - [3.3. run demo1 v2](#33-run-demo1-v2)
- [4. 整合HTTP Server](#4-整合http-server)
    - [4.1. Apache](#41-apache)
        - [4.1.1. Apache + mod_wsgi](#411-apache--mod_wsgi)
    - [4.2. Nginx](#42-nginx)

<!-- /TOC -->

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
