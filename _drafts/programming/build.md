[Home](/)

<!-- TOC -->

    - [1. Demo](#1-demo)
        - [1.1. perl](#1-1-perl)
    - [2. Installation](#2-installation)
        - [2.1. C/C++](#2-1-c-c)
            - [3.1.1. conan](#3-1-1-conan)
        - [2.2. PHP](#2-2-php)
        - [2.3. Python](#2-3-python)
    - [Build Tools](#build-tools)
        - [Java: Maven](#java-maven)
    - [3. Package Management](#3-package-management)
        - [3.2. Search](#3-2-search)
        - [3.3. Install/Remove](#3-3-install-remove)
            - [3.3.1. pip](#3-3-1-pip)
            - [3.3.2. cpan](#3-3-2-cpan)
        - [3.4. upgrade](#3-4-upgrade)
    - [4. 多版本共存问题](#4)
        - [4.1. Demo](#4-1-demo)
            - [4.1.1. Python](#4-1-1-python)
        - [4.2. Python](#4-2-python)
        - [4.3. Ruby: RVM](#4-3-ruby-rvm)
        - [4.4. PHP?](#4-4-php)
        - [4.5. Perl?](#4-5-perl)
- [打包与发布](#)
        - [4.6. Java: jar & war](#4-6-java-jar-war)
        - [4.7. Python: wheel](#4-7-python-wheel)
    - [5. Porting](#5-porting)
        - [5.1. GCC cross-compiling](#5-1-gcc-cross-compiling)
        - [5.2. Go cross-compiling](#5-2-go-cross-compiling)
        - [5.3. Rust cross-compiling](#5-3-rust-cross-compiling)
    - [6. Build Compiler/VM/Intepretor](#6-build-compiler-vm-intepretor)
    - [Unit Test](#unit-test)

<!-- /TOC -->

## 1. Demo

### 1.1. perl

```perl
my $now = localtime();
print "current time is $now.";
```

## 2. Installation

### 2.1. C/C++

#### 3.1.1. conan

### 2.2. PHP

Windows

```powershell
choco install -y php
# uncomment the following line in C:\tools\php71\php.ini
# extension=php_openssl.dll
choco install -y composer
```

CentOS:

```bash

```


post installation for all unix-like systems:

```bash
mkdir -p $HOME/.composer/vendor/bin
# export PATH=$PATH:$HOME/.composer/vendor/bin
echo 'export PATH=$PATH:$HOME/.composer/vendor/bin' >> .bashrc
```

### 2.3. Python


## Build Tools

### Java: Maven

```bash
mvn exec:java -Dexec.mainClass=$class
```

## 3. Package Management

### 3.2. Search

### 3.3. Install/Remove

#### 3.3.1. pip

据[官方文档](https://pip.pypa.io/en/latest/installing)说python 2.7.9+/3.4+都内建支持pip

疑惑：我在CentOS和Ubuntu两种系统上测试，结果都是“否”。难道仅指"import pip"？

#### 3.3.2. cpan

install perl-CGI module

```bash
cpan (or "sudo cpan")
cpan> install CGI
```

or:

```bash
perl -MCPAN -e "install CGI"
```

test the module installation
```

#!/usr/bin/perl -w

use CGI;

print "$CGI::VERSION";

print header;
```

### 3.4. upgrade

## 4. 多版本共存问题

### 4.1. Demo

#### 4.1.1. Python

demo.py

```python
import sys, platform

info = sys.executable + ': ' + platform.python_version()

print(info)
```

### 4.2. Python

pyenv(deprecated), venv, virtualenv, virtualenvwrapper, Anaconda

utility | powerful | function comparison | comments
------------|----------|-----------------|--------
venv | :thumbsup: | only support current python version | python 3.3+ built-in, light weighted
virtualenv | :thumbsup::thumbsup: | + support any installed version of python |
virtualenvwrapper | :thumbsup::thumbsup::thumbsup: | + feasible utilities | suitable for most application
anaconda | :thumbsup::thumbsup::thumbsup::thumbsup: | + support any version of python<br/> + integrate computing packages | suitable for science computing

**venv:**

python 3.3+ built-in

```bash
python -m venv /PATH/TO/ENV
cd /YOUR/WORKING/DIRECTORY
. /PATH/TO/ENV/bin/activate ('.' is not needed for Windows)
python --version
# other work
deactivate
```

**virtualenv:**

```bash
virtualenv -p PYTHON.exe --no-site-packages /PATH/TO/ENV
# same with venv
```

**virtualenvwrapper:**

append to profile (.bashrc):

```bash
export WORKON_HOME=$HOME/envs
```

**Anaconda**

*安装略*
若是初学者，建议装完后注销以使环境变量生效

*使用举例*

```bash
conda create -n env1 python=2.7
conda create -n env2 python=3.6

source activate env1
python --version
python demo.py

source activate env2
python --version
python demo.py

source deactivate
```

建议：launch your editor or IDE from inside the virtualenv to inherit the environment configuration


### 4.3. Ruby: RVM

### 4.4. PHP?

http://stackoverflow.com/questions/524508/how-can-one-run-multiple-versions-of-php-5-x-on-a-development-lamp-server

http://askubuntu.com/questions/50344/how-to-have-two-version-of-php-installed-and-switch-easily

### 4.5. Perl?

# 打包与发布

### 4.6. Java: jar & war

### 4.7. Python: wheel

## 5. Porting

### 5.1. GCC cross-compiling

### 5.2. Go cross-compiling

### 5.3. Rust cross-compiling

## 6. Build Compiler/VM/Intepretor

[Home](/)

```bash
# CentOS 6/7:
curl https://setup.ius.io | sudo sh # install ISU first
sudo yum install -y python35u python35u-pip python35u-devel # or python27u
sudo python3.5 -m pip install virtualenvwrapper
sudo su -c "echo 'export VIRTUALENVWRAPPER_PYTHON=/usr/bin/python3.5' >> /etc/profile" # optional

# Ubuntu:
apt install -y python35-dev virtualenvwrapper

# ArchLinux:

# Gentoo:

# FreeBSD:
pkg install -y virtualenvwrapper # TBC

# macOS:
brew install pyenv-virtualenvwrapper
```

## Unit Test