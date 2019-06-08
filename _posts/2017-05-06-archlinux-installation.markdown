---
layout: post
title: "ArchLinux系统安装（史上最棒的ArchLinux安装指导）"
date: "2017-05-06 11:43:32 +0800"
---

[点击此处可加入相关讨论群](https://jq.qq.com/?_wv=1027&k=477ADMC)。
本文在ArchLinux with Gnome环境上撰写。
<br/>
![](/res/archlinux/archlinux.png)

<!-- TOC -->

- [1. 概述](#1-概述)
    - [1.1. 本教程的特点](#11-本教程的特点)
    - [1.2. 各阶段的基本目标](#12-各阶段的基本目标)
    - [1.3. 阅读指引](#13-阅读指引)
- [2. ArchLinux安装之第一阶段：最小系统](#2-archlinux安装之第一阶段最小系统)
    - [2.1. 准备工作](#21-准备工作)
    - [2.2. 启动系统并做必要的检测](#22-启动系统并做必要的检测)
    - [2.3. SSH登录（推荐，非必需）](#23-ssh登录推荐非必需)
    - [2.4. 更新软件包安装源（ArchLinux的App Store）](#24-更新软件包安装源archlinux的app-store)
    - [2.5. 创建分区](#25-创建分区)
    - [2.6. 创建文件系统（即格式化）](#26-创建文件系统即格式化)
    - [2.7. 生成rootfs](#27-生成rootfs)
    - [2.8. 切换到目标系统（chroot）](#28-切换到目标系统chroot)
    - [2.9. 配置locale](#29-配置locale)
    - [2.10. 安装必备的service](#210-安装必备的service)
    - [2.11. 设置root用户密码](#211-设置root用户密码)
    - [2.12. 更新initrd](#212-更新initrd)
    - [2.13. 安装Grub](#213-安装grub)
    - [2.14. reboot](#214-reboot)
- [3. ArchLinux安装之第二阶段：完善基于Text模式的ArchLinux](#3-archlinux安装之第二阶段完善基于text模式的archlinux)
    - [3.1. 以root用户登录并做必要的检测](#31-以root用户登录并做必要的检测)
    - [3.2. 创建普通用户](#32-创建普通用户)
    - [3.3. SSH登录（推荐，非必须）](#33-ssh登录推荐非必须)
    - [3.4. 安装bash completion](#34-安装bash-completion)
    - [3.5. 设置hostname](#35-设置hostname)
    - [3.6. 安装编辑器](#36-安装编辑器)
    - [3.7. 安装常用开发工具](#37-安装常用开发工具)
    - [3.8. 安装yaourt](#38-安装yaourt)
- [4. ArchLinux安装之第三阶段：安装GUI桌面系统](#4-archlinux安装之第三阶段安装gui桌面系统)
    - [4.1. 安装Xorg](#41-安装xorg)
    - [4.2. WM方案1: Gnome](#42-wm方案1-gnome)
    - [4.3. WM方案2: KDE](#43-wm方案2-kde)
    - [4.4. 安装open-vm-tools（仅限于VMWare上安装ArchLinux）](#44-安装open-vm-tools仅限于vmware上安装archlinux)

<!-- /TOC -->



## 1. 概述

### 1.1. 本教程的特点
1. 所有步骤均已测试过，以保证博文本身的正确性。
1. 每个安装步骤均附带"double check"方法，帮助您保证自己实际操作时的正确性。
1. 引入SSH方式，高效又准确。通过SSH客户端，既可以直接复制文档中的步骤到终端中执行，也可以（在遇到问题时）从终端中复制信息去google或发到讨论群中，甚至截屏 :smile:
1. 文档与脚本两者同步，看文档的同时不但可以读脚本，还可以用脚本一键完成全部安装工作！
1. 所有驱动完整工作（多台机器测试）。
1. Linux内核精确定制（多台机器测试）。
1. 同时支持物理及和虚拟机，同时支持GPT和DOS两种分区方式。

### 1.2. 各阶段的基本目标
第一阶段：安装基本系统。用最少最简单的步骤跑起一个基本系统，这样做的好处是：即便是从未接触过ArchLinux的同学也能顺利迈出第一步。

第二阶段：完善基于Text模式的ArchLinux。在第一阶段的基础上把进一步完善系统，但仅限Text模式，不考虑GUI。一方面，Text模式下可以更好的理解ArchLinux的工作方式；另一方面，也是出于服务器部署的考虑。

第三阶段：安装GUI桌面系统。

### 1.3. 阅读指引
对于有SSH条件的小伙伴，**强烈建议完成2.3/3.3节操作，从而通过远程SSH来完成后续步骤**。

<!--对于有SSH条件的小伙伴，**强烈建议完成第3步操作，从而第3～7步全在远程系统上通过SSH来完成**；否则可以忽略第3步，直接在本机上继续操作第4步。-->
<!-- （推荐做法，但对于没有SSH条件的同学可跳过这一步) -->


## 2. ArchLinux安装之第一阶段：最小系统


### 2.1. 准备工作
先从[ArchLinux官网](https://www.archlinux.org)或者[某个镜像网站](http://mirrors.zju.edu.cn)
下载ArchLinux ISO。
-   若安装在物理机上，需要制作一个USB安装盘，具体方法请google<!-- - 或参考[WitBox](https://github.com/conke/witbox) -->
-   若安装在虚拟机上，可直接使用ISO。

### 2.2. 启动系统并做必要的检测
检查网络连接
```bash
ping aliyun.com
```

确认分区类型，即GPT还是DOS。如果/sys/firmware/efi目录非空，则采用GPT，否则用DOS。
```bash
ls /sys/firmware/efi
```

检查时间日期：
```bash
date
```

如果时间日期不准确，则需要用下面的命令修正：
```bash
timedatectl set-ntp true
timedatectl status
date
```

### 2.3. SSH登录（推荐，非必需）
LiveCD上开启SSH服务并设置root用户密码：
```bash
systemctl start sshd
passwd
```

Double check:
```bash
ssh localhost
ip addr # 请记住该IP，后面将有数次操作均需要用到它。
ssh root@IP
exit
```

从另一台装有SSH客户段的机器（PC/虚拟机/平板均可）上用如下命令登录本机。其中IP为上面查看到的IP地址。
```bash
ssh root@IP
```
<!-- 本博文（即[第一阶段](http://conke.github.io/system/archlinux/introduction) -->
接下来所有操作均在远程机器上完成。

### 2.4. 更新软件包安装源（ArchLinux的App Store）
输入下面的命令以选择中国国内的镜像（SSH 方式下可直接复制粘帖）：
```bash
cp -v /etc/pacman.d/mirrorlist{,.orig}
sed -n '/China/{p;n;p}' /etc/pacman.d/mirrorlist.orig > /etc/pacman.d/mirrorlist
````

Double check:
```bash
cat /etc/pacman.d/mirrorlist
```

刷新：
```bash
pacman -Sy
```

### 2.5. 创建分区

分区规划：

No.|Type|Size|Comments
---|----|----|------
1|EFI System|128M|DOS分区方式不需要创建该分区
2|Linux swap|RAM size x 2| 推荐大小为实际物理内存的2倍
3|Linux filesystem|(剩余大小)|

然后使用cfdisk工具进行分区：
<!--
echo -e "o\nn\n\n\n\n+4G\nn\n\n\n\n\nw\n" | fdisk /dev/sda (for MBR/DOS partition)
 -->

```bash
cfdisk /dev/sda
```
GPT分区结果应该如下所示：
![part](/res/archlinux/part.png)

Double check:
```bash
fdisk -l /dev/sda
```
请注意大小和类型，要和上图一致

### 2.6. 创建文件系统（即格式化）
```bash
mkfs.vfat -F 32 -n EFI /dev/sda1 # DOS分区方式不需要执行该步骤
mkswap -L SWAP /dev/sda2
mkfs.ext4 -L ROOT /dev/sda3
```

Double check:
```bash
blkid
```
结果应该如下所示：
![blkid](/res/archlinux/blkid.png)


### 2.7. 生成rootfs
开启swap：
```bash
swapon LABEL=SWAP
swapon
```

mount ROOT分区到和EFI分区：
```bash
mount LABEL=ROOT /mnt
mkdir -p /mnt/boot/efi # DOS分区方式不需要执行这条及下一条命令
mount LABEL=EFI /mnt/boot/efi
```

Double check:
```bash
mount
```
看到类似"/dev/sdaN on /mnt type ext4"这样的记录则说明当前操作结果正确。


在ROOT分区上开始生成基本系统：
```bash
pacstrap /mnt base
```

Double check:
```bash
ls /mnt
```

自动生成fstab：
```bash
genfstab -U -p /mnt # check
genfstab -U -p /mnt >> /mnt/etc/fstab
```
genfstab工具确实方便，我打算为Gentoo写一个 :smile:

Double check:
```bash
cat /mnt/etc/fstab
```

### 2.8. 切换到目标系统（chroot）
```bash
arch-chroot /mnt
```

Double check:
```bash
mount
```
看到之前"/dev/sdaN on /mnt type ext4"那条记录已变为"/dev/sdaN on / type ext4"则说明当前操作结果正确，当然，使用GPT，还需要确认存在”/boot/efi”记录项。

### 2.9. 配置locale
配置locale:
```bash
ln -svf /usr/share/zoneinfo/Asia/Shanghai /etc/localtime
hwclock --systohc --utc
sed -i 's/^#\(en_US.UTF-8\)/\1/' /etc/locale.gen
locale-gen
echo "LANG=en_US.UTF-8" > /etc/locale.conf
```

Double check:
```bash
locale
cat /etc/locale.conf
```

### 2.10. 安装必备的service
```bash
pacman -S openssh syslog-ng
systemctl enable sshd syslog-ng dhcpcd
```

Double check:
```bash
systemctl list-unit-files | grep sshd # or syslog-ng/dhcpcd
```

### 2.11. 设置root用户密码
之前设置的是LiveCD系统上的root密码，这一步设置的则是安装后目标系统上的root密码。
```bash
passwd
```

Double check:
```bash
ssh localhost
exit
```

### 2.12. 更新initrd
```bash
mkinitcpio -p linux
```

Double check:
```bash
???
```

### 2.13. 安装Grub
```bash
pacman -S grub efibootmgr # DOS分区方式不需要安装efibootmgr
grub-install /dev/sda # FIXME
grub-mkconfig -o /boot/grub/grub.cfg
```

Double check:
```bash
ls /boot/grub
ls /boot/efi
cat /boot/grub/grub.cfg
```

<!-- pacman -S intel-ucode # for Intel CPU only -->

### 2.14. reboot
```bash
exit
umount /mnt/boot/efi # DOS分区方式不需要执行该步骤
umount /mnt
reboot
```

## 3. ArchLinux安装之第二阶段：完善基于Text模式的ArchLinux

### 3.1. 以root用户登录并做必要的检测
检查网络连接
```bash
ip addr
ping aliyun.com
```

检查SSH服务
```bash
systemctl status sshd
```

检查locale设置
```bash
localectl status
```
<!--
```bash
localectl list-locales
localectl set-locale LANG="en_US.utf8"
```
 -->

检查syslog
```bash
cat /var/log/syslog.log
```

上面工作同时隐含了对systemd的检查。

### 3.2. 创建普通用户
添加用户，示例如下：

```bash
u=conke
g=maxwit

groupadd $g
useradd -g $g -G wheel -c 'Conke Hu' -m $u
passwd $u
```

Double check:
```bash
ssh $u@IP ls # IP地址可用"ip addr"命令查看
```

安装sudo
```bash
pacman -S sudo
```

开启wheel组的权限：
```bash
nano /etc/sudoers
```
然后找到以“%wheel”开头并包含“NOPASSWD”的那一行，然后去掉行首的”#”，保存退出。其中NOPASSWD表示执行sudo时不会提示输入密码。
Double check:
```bash
su - $u
sudo ls
exit
```

### 3.3. SSH登录（推荐，非必须）
从另一台装有SSH客户段的机器（PC/虚拟机/平板均可）上用如下命令登录本机。其中，myname为你的用户名；其中ip为上面开始时查看到的IP地址，如果已忘记可用"ip addr"命令重新查看。
```bash
ssh myname@ip
sudo su -
```

### 3.4. 安装bash completion

### 3.5. 设置hostname
```bash
hn=myhostname
hostnamectl set-hostname $hn
sed -i "s/\(^127.0.0.1.*localhost$\)/\1 $hn/" /etc/hosts
```

Double check:
```bash
hostname
ping $hn
```

### 3.6. 安装编辑器
```bash
pacman -S vim emacs
rm /bin/vi
cp /usr/bin/vim /bin/vi
```

Double check:
```
vi
emacs
```


### 3.7. 安装常用开发工具
```bash
pacman -S base-devel git
```

Double check:
```bash
gcc -v
git
```

### 3.8. 安装yaourt
回到普通用户模式：
```bash
exit
```

Double check: 注意提示符从“#”变回了“$”！


```bash
git clone https://aur.archlinux.org/package-query.git
cd package-query
makepkg -si
cd ..
git clone https://aur.archlinux.org/yaourt.git
cd yaourt
makepkg -si
```

Double check: 用yaourt装一个小工具
```bash
yaourt tree
```

<!-- ### 3.9. 配置VPN -->
AUR包太丰富了，比Ubuntu还丰富，但很多repo需要翻墙才能下载


## 4. ArchLinux安装之第三阶段：安装GUI桌面系统

### 4.1. 安装Xorg

Install Xorg

```bash
pacman -S xorg xorg-xinit xorg-twm xterm
```

double check:

```bash
startx
```

### 4.2. WM方案1: Gnome

install Gnome

```bash
pacman -S gnome gnome-extra gnome-tweak-tool
```

systemd services

```bash
systemctl enable gdm NetworkManager
```

reboot (optional)

### 4.3. WM方案2: KDE

```bash
TODO
```

### 4.4. 安装open-vm-tools（仅限于VMWare上安装ArchLinux）

```bash
pacman -S gtkmm open-vm-tools
```

在当前目录下新建一.service文件，比如取名为hgfs.service，内容如下

```ini
[Unit]
Description=VMware Shared Folders
Requires=vmware-vmblock-fuse.service
After=vmware-vmblock-fuse.service
ConditionPathExists=/mnt/hgfs
ConditionVirtualization=vmware

[Service]
Type=oneshot
RemainAfterExit=yes
ExecStart=/usr/bin/vmhgfs-fuse -o allow_other -o auto_unmount .host:/ /mnt/hgfs

[Install]
WantedBy=multi-user.target
```

然后启动hgfs服务:

```bash
mkdir -p /mnt/hgfs
cp -v hgfs.service /etc/systemd/system/
systemctl enable hgfs
```

Double check:

```bash
systemctl start hgfs
ls /mnt/hgfs
```

```bash
sed -i 's/^#\(Waylang\)\1/' /etc/gdm/custom.conf
```
