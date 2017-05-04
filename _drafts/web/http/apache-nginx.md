[Home](/)

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

[Home](/)
