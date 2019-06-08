---
layout: post
title: "Linux/Windows/macOS/FreeBSD系统高手"
date: "2017-05-06 10:41:45 +0800"
---

《料理鼠王》里有句经典台词："Not any system expert can become a R&D expert, but a R&D expert can come from system experts."

<!-- TOC -->

- [1. User and Group](#1-user-and-group)
    - [1.1. change group](#11-change-group)
    - [1.2. Default shell (login shell)](#12-default-shell-login-shell)
    - [1.3. CLI: Linux vs BSD](#13-cli-linux-vs-bsd)
- [2. Block device and file system](#2-block-device-and-file-system)
    - [2.1. block device info](#21-block-device-info)
        - [2.1.1. mount](#211-mount)
- [3. Network](#3-network)
    - [3.1. Utilities](#31-utilities)
    - [3.2. VPN](#32-vpn)
    - [3.3. host name](#33-host-name)
    - [3.4. Remote Access](#34-remote-access)
    - [3.5. SSH](#35-ssh)
        - [3.5.1. Windows](#351-windows)
        - [3.5.2. Linux/FreeBSD](#352-linuxfreebsd)
        - [3.5.3. macOS](#353-macos)
        - [3.5.4. Client](#354-client)
    - [3.6. VNC](#36-vnc)
        - [3.6.1. Windows](#361-windows)
        - [3.6.2. Linux/FreeBSD](#362-linuxfreebsd)
        - [3.6.3. macOS](#363-macos)
        - [3.6.4. Client](#364-client)
    - [3.7. RDP](#37-rdp)
        - [3.7.1. Server (Windows only)](#371-server-windows-only)
        - [3.7.2. Client](#372-client)
    - [3.8. X11](#38-x11)
        - [3.8.1. Server (Unix-like only)](#381-server-unix-like-only)
            - [3.8.1.1. Client](#3811-client)
- [4. Zabbix](#4-zabbix)
- [5. Backup and Restore](#5-backup-and-restore)
- [6. SeLinux](#6-selinux)
- [7. D-Bus](#7-d-bus)
- [8. Init](#8-init)
    - [8.1. systemd and OpenRC](#81-systemd-and-openrc)
    - [8.2. systemd sucks?](#82-systemd-sucks)
    - [8.3. References](#83-references)
- [9. Package management](#9-package-management)
    - [9.1. Search](#91-search)
        - [9.1.1. dpkg/apt](#911-dpkgapt)
        - [9.1.2. rpm/yum/dnf](#912-rpmyumdnf)
        - [9.1.3. emerge](#913-emerge)
        - [9.1.4. pacman](#914-pacman)
        - [9.1.5. yaourt](#915-yaourt)
        - [9.1.6. brew](#916-brew)
        - [9.1.7. choco](#917-choco)
        - [9.1.8. pkg](#918-pkg)
    - [9.2. Install/remove](#92-installremove)
    - [9.3. List content](#93-list-content)
        - [9.3.1. dpkg/apt-get/apt](#931-dpkgapt-getapt)
        - [9.3.2. rpm/yum/dnf](#932-rpmyumdnf)
        - [9.3.3. emerge](#933-emerge)
        - [9.3.4. pacman](#934-pacman)
        - [9.3.5. yaourt](#935-yaourt)
        - [9.3.6. brew](#936-brew)
        - [9.3.7. choco](#937-choco)
        - [9.3.8. pkg](#938-pkg)
    - [9.4. Build from source](#94-build-from-source)
- [10. Hardware](#10-hardware)
    - [10.1. CPU](#101-cpu)
        - [10.1.1. flags](#1011-flags)
    - [10.2. GPU](#102-gpu)
    - [10.3. PCI Bus](#103-pci-bus)
        - [10.3.1. list](#1031-list)
        - [10.3.2. driver attached](#1032-driver-attached)
    - [10.4. USB Bus](#104-usb-bus)
        - [10.4.1. list](#1041-list)
    - [10.5. Bluetooth and WiFi](#105-bluetooth-and-wifi)
    - [10.6. Storage](#106-storage)
    - [10.7. Benchmark](#107-benchmark)
- [11. Kernel and modules](#11-kernel-and-modules)
    - [11.1. Kernel](#111-kernel)
    - [11.2. Kernel modules](#112-kernel-modules)
        - [11.2.1. list modules](#1121-list-modules)
- [12. System service](#12-system-service)
    - [12.1. List and Status](#121-list-and-status)
        - [12.1.1. Linux initrc](#1211-linux-initrc)
        - [12.1.2. Linux systemd](#1212-linux-systemd)
        - [12.1.3. Windows](#1213-windows)
        - [12.1.4. macOS](#1214-macos)
        - [12.1.5. FreeBSD](#1215-freebsd)
    - [12.2. Enable/Disable](#122-enabledisable)
        - [12.2.1. Linux initrc](#1221-linux-initrc)
        - [12.2.2. Linux systemd](#1222-linux-systemd)
        - [12.2.3. Windows](#1223-windows)
        - [12.2.4. macOS](#1224-macos)
        - [12.2.5. FreeBSD](#1225-freebsd)
    - [12.3. Start/Stop](#123-startstop)
        - [12.3.1. Linux initrc](#1231-linux-initrc)
        - [12.3.2. Linux systemd](#1232-linux-systemd)
        - [12.3.3. Windows](#1233-windows)
        - [12.3.4. macOS](#1234-macos)
        - [12.3.5. FreeBSD](#1235-freebsd)
    - [12.4. Create/Delete](#124-createdelete)
        - [12.4.1. Linux initrc](#1241-linux-initrc)
        - [12.4.2. Linux systemd](#1242-linux-systemd)
        - [12.4.3. Windows](#1243-windows)
        - [12.4.4. macOS](#1244-macos)
        - [12.4.5. FreeBSD](#1245-freebsd)
    - [12.5. Edit/Modify](#125-editmodify)
        - [12.5.1. Linux initrc](#1251-linux-initrc)
        - [12.5.2. Linux systemd](#1252-linux-systemd)
        - [12.5.3. Windows](#1253-windows)
        - [12.5.4. macOS](#1254-macos)
        - [12.5.5. FreeBSD](#1255-freebsd)

<!-- /TOC -->

# 1. User and Group

## 1.1. change group

FreeBSD

```bash
pw group mod group_name -m user_name
```

## 1.2. Default shell (login shell)

- Unix-like通用方式

```bash
chsh -s /usr/bin/zsh $USER
```
- Linux特有方式

```bash
usermod -s /usr/bin/zsh $USER
```
- macOS/FreeBSD特有方式

```bash
chpass -s /usr/bin/zsh $USER
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

# 3. Network

## 3.1. Utilities
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


## 3.4. Remote Access


Protocol | Port | Host | Comments
---------|------|------|---------
SSH | 22 | All |
RDP | 3389 | Windows |
VNC | 5900 | All |
X11 | 6000 | Unix | ?

## 3.5. SSH

### 3.5.1. Windows

### 3.5.2. Linux/FreeBSD

### 3.5.3. macOS

### 3.5.4. Client

## 3.6. VNC

### 3.6.1. Windows

### 3.6.2. Linux/FreeBSD

### 3.6.3. macOS

### 3.6.4. Client

## 3.7. RDP

### 3.7.1. Server (Windows only)

system > Advanced system settings

![](/res/system/net/rdp-setting.png)

To change the default port:

![](/res/system/net/rdp-port.png)

### 3.7.2. Client

windows: remote desktop connection

linux: vinagre

## 3.8. X11

### 3.8.1. Server (Unix-like only)

#### 3.8.1.1. Client



# 4. Zabbix


# 5. Backup and Restore

# 6. SeLinux
for archlinux and gentoo

# 7. D-Bus

# 8. Init

## 8.1. systemd and OpenRC

Failed to get D-Bus connection

## 8.2. systemd sucks?


## 8.3. References
- https://dbus.freedesktop.org/doc/dbus-tutorial.html


# 9. Package management


operation | dpkg/apt-get/apt | rpm/yum/dnf | emerge | pacman/yaourt | brew | choco | pkg
----------|------------------|-------------|--------|---------------|------|-------|-----
search
install/remove
list content
build from source

## 9.1. Search

### 9.1.1. dpkg/apt

### 9.1.2. rpm/yum/dnf

```bash
yumdb search from_repo ius python
```

### 9.1.3. emerge

### 9.1.4. pacman

### 9.1.5. yaourt

### 9.1.6. brew

### 9.1.7. choco

### 9.1.8. pkg

## 9.2. Install/remove

## 9.3. List content

### 9.3.1. dpkg/apt-get/apt

### 9.3.2. rpm/yum/dnf

```bash
rpm -ql postgresql-server
```

### 9.3.3. emerge

### 9.3.4. pacman

### 9.3.5. yaourt

### 9.3.6. brew

### 9.3.7. choco

### 9.3.8. pkg

## 9.4. Build from source


pacman -Ql 本地 ; pacman -Fl 仓库

http://docs.brew.sh/Interesting-Taps-&-Forks.html

# 10. Hardware

## 10.1. CPU

### 10.1.1. flags

## 10.2. GPU

## 10.3. PCI Bus

### 10.3.1. list

### 10.3.2. driver attached

## 10.4. USB Bus

### 10.4.1. list

## 10.5. Bluetooth and WiFi

## 10.6. Storage

## 10.7. Benchmark

# 11. Kernel and modules

## 11.1. Kernel

## 11.2. Kernel modules

### 11.2.1. list modules

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

# 12. System service

## 12.1. List and Status

### 12.1.1. Linux initrc

### 12.1.2. Linux systemd

### 12.1.3. Windows

### 12.1.4. macOS

### 12.1.5. FreeBSD

## 12.2. Enable/Disable

### 12.2.1. Linux initrc

### 12.2.2. Linux systemd

### 12.2.3. Windows

### 12.2.4. macOS

### 12.2.5. FreeBSD

## 12.3. Start/Stop

### 12.3.1. Linux initrc

### 12.3.2. Linux systemd

### 12.3.3. Windows

### 12.3.4. macOS

### 12.3.5. FreeBSD

## 12.4. Create/Delete

### 12.4.1. Linux initrc

### 12.4.2. Linux systemd

### 12.4.3. Windows

### 12.4.4. macOS

### 12.4.5. FreeBSD

## 12.5. Edit/Modify

### 12.5.1. Linux initrc

### 12.5.2. Linux systemd

### 12.5.3. Windows

### 12.5.4. macOS

### 12.5.5. FreeBSD
