---
layout: post
title: "Linux/Windows/macOS/FreeBSD系统高手"
date: "2017-05-06 10:41:45 +0800"
---

《料理鼠王》里有句经典台词："Not any system expert can become a R&D expert, but a R&D expert can come from system experts."


<!-- TOC -->

- [1. User and Group](#1-user-and-group)
    - [1.1. change group](#1-1-change-group)
    - [1.2. Default shell (login shell)](#1-2-default-shell-login-shell)
    - [1.3. CLI: Linux vs BSD](#1-3-cli-linux-vs-bsd)
- [2. Block device and file system](#2-block-device-and-file-system)
    - [2.1. block device info](#2-1-block-device-info)
        - [2.1.1. mount](#2-1-1-mount)
- [3. 网络连接](#3)
    - [3.1. 基本工具](#3-1)
    - [3.2. VPN](#3-2-vpn)
    - [3.3. host name](#3-3-host-name)
- [4. Remote Access](#4-remote-access)
    - [4.1. Overview](#4-1-overview)
    - [4.2. SSH](#4-2-ssh)
        - [4.2.2. Windows](#4-2-2-windows)
        - [4.2.3. Linux/FreeBSD](#4-2-3-linux-freebsd)
        - [4.2.4. macOS](#4-2-4-macos)
        - [4.2.5. Client](#4-2-5-client)
    - [4.3. VNC](#4-3-vnc)
        - [4.3.1. Windows](#4-3-1-windows)
        - [4.3.2. Linux/FreeBSD](#4-3-2-linux-freebsd)
        - [4.3.3. macOS](#4-3-3-macos)
        - [4.3.4. Client](#4-3-4-client)
    - [4.4. RDP](#4-4-rdp)
        - [4.4.1. Server (Windows only)](#4-4-1-server-windows-only)
        - [4.4.2. Client](#4-4-2-client)
    - [4.5. X11](#4-5-x11)
        - [4.5.1. Server (Unix-like only)](#4-5-1-server-unix-like-only)
            - [4.5.1.1. Client](#4-5-1-1-client)
- [5. Zabbix](#5-zabbix)
- [6. Backup and Restore](#6-backup-and-restore)
- [7. SeLinux](#7-selinux)
- [8. D-Bus](#8-d-bus)
- [9. Init](#9-init)
    - [9.1. systemd and OpenRC](#9-1-systemd-and-openrc)
    - [9.2. systemd sucks?](#9-2-systemd-sucks)
    - [9.3. References](#9-3-references)
- [10. Package management](#10-package-management)
- [11. Hardware](#11-hardware)
    - [11.1. CPU](#11-1-cpu)
        - [11.1.2. flags](#11-1-2-flags)
    - [11.2. GPU](#11-2-gpu)
    - [11.3. PCI Bus](#11-3-pci-bus)
        - [11.3.1. list](#11-3-1-list)
        - [11.3.2. driver attached](#11-3-2-driver-attached)
    - [11.4. USB Bus](#11-4-usb-bus)
        - [11.4.1. list](#11-4-1-list)
    - [11.5. Bluetooth and WiFi](#11-5-bluetooth-and-wifi)
    - [11.6. Storage](#11-6-storage)
    - [11.7. Benchmark](#11-7-benchmark)
- [12. Kernel and modules](#12-kernel-and-modules)
    - [12.1. Kernel](#12-1-kernel)
    - [12.2. Kernel modules](#12-2-kernel-modules)
        - [12.2.1. list modules](#12-2-1-list-modules)
- [13. System service](#13-system-service)
    - [13.1. List and Status](#13-1-list-and-status)
        - [13.1.2. Linux initrc](#13-1-2-linux-initrc)
        - [13.1.3. Linux systemd](#13-1-3-linux-systemd)
        - [13.1.4. Windows](#13-1-4-windows)
        - [13.1.5. macOS](#13-1-5-macos)
        - [13.1.6. FreeBSD](#13-1-6-freebsd)
    - [13.2. Enable/Disable](#13-2-enable-disable)
        - [13.2.1. Linux initrc](#13-2-1-linux-initrc)
        - [13.2.2. Linux systemd](#13-2-2-linux-systemd)
        - [13.2.3. Windows](#13-2-3-windows)
        - [13.2.4. macOS](#13-2-4-macos)
        - [13.2.5. FreeBSD](#13-2-5-freebsd)
    - [13.3. Start/Stop](#13-3-start-stop)
        - [13.3.1. Linux initrc](#13-3-1-linux-initrc)
        - [13.3.2. Linux systemd](#13-3-2-linux-systemd)
        - [13.3.3. Windows](#13-3-3-windows)
        - [13.3.4. macOS](#13-3-4-macos)
        - [13.3.5. FreeBSD](#13-3-5-freebsd)
    - [13.4. Create/Delete](#13-4-create-delete)
        - [13.4.1. Linux initrc](#13-4-1-linux-initrc)
        - [13.4.2. Linux systemd](#13-4-2-linux-systemd)
        - [13.4.3. Windows](#13-4-3-windows)
        - [13.4.4. macOS](#13-4-4-macos)
        - [13.4.5. FreeBSD](#13-4-5-freebsd)
    - [13.5. Edit/Modify](#13-5-edit-modify)
        - [13.5.1. Linux initrc](#13-5-1-linux-initrc)
        - [13.5.2. Linux systemd](#13-5-2-linux-systemd)
        - [13.5.3. Windows](#13-5-3-windows)
        - [13.5.4. macOS](#13-5-4-macos)
        - [13.5.5. FreeBSD](#13-5-5-freebsd)

<!-- /TOC -->

# 1. User and Group

## 1.1. change group

FreeBSD

```bash
pw group mod group_name -m user_name
```

## 1.2. Default shell (login shell)

- FreeBSD/macOS

```bash
chpass -s /usr/loca/bin/bash $user
```

- Linux -> PowerShell

```bash
usermod -s /usr/bin/powershell $user
```

## 1.3. CLI: Linux vs BSD

No.|Function|Linux|BSD|Comments
---|--------|-----|-------|--------
1|add/del user(s)|useradd<br/>userdel|adduser<br/>(?)|what about macOS?
1|change user info|usermod|chpass|
1|ls with color|ls --color|export CLICOLOR=1|


# 2. Block device and file system

## 2.1. block device info

_Windows_

_Linux_
```
fdisk
blkid
```

_macOS_
```
diskutil
```

_FreeBSD_

### 2.1.1. mount

_Windows_



_Linux_

_macOS_
```bash
diskutil
```

# 3. 网络连接

## 3.1. 基本工具
- https://en.wikipedia.org/wiki/Iproute2


## 3.2. VPN
```bash
/usr/lib/networkmanager/nm-l2tp-service --debug
```

## 3.3. host name

_Windows_
```PowerShell
?
```

_Linux_
```bash
hostnamectl
```

_macOS_

```
scutil –-set HostName localhost
```


# 4. Remote Access

## 4.1. Overview

Protocol | Port | Host | Comments
---------|------|------|---------
SSH | 22 | All |
RDP | 3389 | Windows |
VNC | 5900 | All |
X11 | 6000 | Unix | ?

## 4.2. SSH

### 4.2.2. Windows

### 4.2.3. Linux/FreeBSD

### 4.2.4. macOS

### 4.2.5. Client

## 4.3. VNC

### 4.3.1. Windows

### 4.3.2. Linux/FreeBSD

### 4.3.3. macOS

### 4.3.4. Client

## 4.4. RDP

### 4.4.1. Server (Windows only)

system > Advanced system settings

![](/res/system/net/rdp-setting.png)

To change the default port:

![](/res/system/net/rdp-port.png)

### 4.4.2. Client

windows: remote desktop connection

linux: vinagre

## 4.5. X11

### 4.5.1. Server (Unix-like only)

#### 4.5.1.1. Client



# 5. Zabbix


# 6. Backup and Restore

# 7. SeLinux
for archlinux and gentoo

# 8. D-Bus

# 9. Init

## 9.1. systemd and OpenRC

Failed to get D-Bus connection

## 9.2. systemd sucks?


## 9.3. References
- https://dbus.freedesktop.org/doc/dbus-tutorial.html


# 10. Package management


operation | dpkg/apt-get/apt | rpm/yum/dnf | emerge | pacman/yaourt | brew | choco | pkg
----------|------------------|-------------|--------|---------------|------|-------|-----
search
install/remove
list content
build from source

## Search

### dpkg/apt-get/apt

### rpm/yum/dnf

```bash
yumdb search from_repo ius python
```

### emerge

### pacman

### yaourt

### brew

### choco

### pkg

## Install/remove

## List content

### dpkg/apt-get/apt

### rpm/yum/dnf

```bash
rpm -ql postgresql-server
```

### emerge

### pacman

### yaourt

### brew

### choco

### pkg

## Build from source


pacman -Ql 本地 ; pacman -Fl 仓库

http://docs.brew.sh/Interesting-Taps-&-Forks.html

# 11. Hardware

## 11.1. CPU

### 11.1.2. flags

## 11.2. GPU

## 11.3. PCI Bus

### 11.3.1. list

### 11.3.2. driver attached

## 11.4. USB Bus

### 11.4.1. list

## 11.5. Bluetooth and WiFi

## 11.6. Storage

## 11.7. Benchmark

# 12. Kernel and modules

## 12.1. Kernel

## 12.2. Kernel modules

### 12.2.1. list modules

Linux

```bash
lsmod
```

FreeBSD

```bash
kldstat
```

macOS:

Windows:

# 13. System service

## 13.1. List and Status

### 13.1.2. Linux initrc

### 13.1.3. Linux systemd

### 13.1.4. Windows

### 13.1.5. macOS

### 13.1.6. FreeBSD

## 13.2. Enable/Disable

### 13.2.1. Linux initrc

### 13.2.2. Linux systemd

### 13.2.3. Windows

### 13.2.4. macOS

### 13.2.5. FreeBSD

## 13.3. Start/Stop

### 13.3.1. Linux initrc

### 13.3.2. Linux systemd

### 13.3.3. Windows

### 13.3.4. macOS

### 13.3.5. FreeBSD

## 13.4. Create/Delete

### 13.4.1. Linux initrc

### 13.4.2. Linux systemd

### 13.4.3. Windows

### 13.4.4. macOS

### 13.4.5. FreeBSD

## 13.5. Edit/Modify

### 13.5.1. Linux initrc

### 13.5.2. Linux systemd

### 13.5.3. Windows

### 13.5.4. macOS

### 13.5.5. FreeBSD
