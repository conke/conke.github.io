---
layout: post
title: "让天下没有难装的黑苹果（持续更新）"
date: "2017-05-06 04:40:46 +0800"
---

Model | CPU | Audio | HDMI | LAN | WiFi | BT | USB | Type-C/TB | Battery | Sleep | Trackpad | Camera | FaceTime | Comments
------|-----|-------|------|-----|------|----|-----|-----------|---------|-------|----------|--------|----------|---------
Xiaoxinchao 5000 | T | T | T | T | T | T | T | T |
Z7-CT7NA| T |  |  | T | T | T || T | T | T | T | T |  |  |
Inspiron 14 7000 | T | T | T | T | T | T | T | T | T | T | T | T
Z7-CT7NA | T | T | T | T | T | T | T | T | T | T | T | T | T |
AN515 | T | T |   | T | T | T | T | T |   |   | T | T | T |
Z7M-CT7NA | T | T | T | T | T | T | T |
Z7M-KP5GC | T | T | T | T | T | T | T | T | T |
X550JX | | | | | | | | | | | | |  |
Inspiron 5488 |  |  |  |  |  |  |  |  |  |  |  |  |  |
GL552VX | T | T | T | T |  |  | T | T | T | T | T | T | T |
A540U |  |  |  |  |  |  |  |  |  |  |  |  |  |
Inspiron 7472 |  |  |  |  |  |  |  |  |  |  |  |  |  |
A456U |  |  |  |  |  |  |  |  |  |  |  |  |  |
Ideapad 510 |  |  |  |  |  |  |  |  |  |  |  |  |  |
ThinkPad T480 |  |  |  |  |  |  |  |  |  |  |  |  |  |
Inspiron 7559 |  |  |  |  |  |  |  |  |  |  |  |  |  |
JK5S03  |  |  |  |  |  |  |  |  |  |  |  |  |  |

# 1. 第一阶段，基本安装

按如下步骤操作，约9成笔记本能顺利安装

## 1.1. 配置BIOS/EFI
（略）
记下CPU型号

## 1.2. 创建macOS安装盘

erase and partition

```bash
cd /Applications/Install macOS Catalina.app/Contents/Resources
sudo ./createinstallmedia --volume /Volumes/X
```

## 1.3. 下载Clover & Clover Configurator

下载clover configurator:
```bash
brew cask install clover-configurator
```

用clover configurator下载clover:
打开clover confirator -> Install/Update Clover -> Save to desktop -> Check Now

如果网络环境不佳，可转至[clover官网](xxx)下载

## 1.4. 安装clover

"Change install location"选择U盘任意分区

customize -> 勾选“Clover for UEFI only”

UEFI drivers -> Memory fix drivers -> OsxAptioFix3Drv (首先尝试这个驱动)

## 1.5. 初始化config.plist

```bash
git clone https://github.com/RehabMan/OS-X-Clover-Laptop-Config.git --depth 1

cd OS-X-Clover-Laptop-Config
ls *.plist
```
然后根据CPU及相应的iGPU型号选择合适的config文件，copy到EFI/Clover目录，比如：
```bash
cp -v config_UHD630.plist /Volumes/ESP/EFI/CLOVER/config.plist

cd /Volumes/ESP/EFI/Clover
open .
```

然后用clover configurator打开config.plist文件 -> 选择SMBIOS，记下"Product model" -> 点击右下角按钮 -> 选择相同型号

## 1.6. 安装EFI driver
Install Drivers -> 选择"HFSPlus" -> Download

注意：老版本的clover configurator的efi文件下载位置与新版本clover不兼容，需要手动mv
```bash
mv -v drivers64UEFI/HFSPlus.efi drivers/UEFI
```

## 1.7. 安装kext

Kext installer -> 选择Lilu, VirtualSMC(或 FakeSMC), Whatevergreen 3个kext，其他暂时不要选

下载键盘驱动:

https://bitbucket.org/RehabMan/os-x-voodoo-ps2-controller/downloads/

复制到EFI/Clover/kexts/Other目录，最终结果如下：
```
drwxrwxrwx  1 conke  staff  512 Jul  3 15:58 Lilu.kext
drwxrwxrwx  1 conke  staff  512 Jul  3 16:22 SMCBatteryManager.kext
drwxrwxrwx  1 conke  staff  512 Jul  3 16:22 VirtualSMC.kext
drwxrwxrwx@ 1 conke  staff  512 Oct  8  2018 VoodooPS2Controller.kext
drwxrwxrwx  1 conke  staff  512 Jul  3 16:18 WhateverGreen.kext
```

Done，现在可以尝试启动安装macOS了