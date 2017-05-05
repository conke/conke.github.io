---
layout: post
title: "UEFI/EDK2开发快速入门"
date: "2017-05-04 12:44:48 +0800"
---

on Windows/Linux/macOS

### EDK2开发环境

_Windows_
```powershell
```

_Linux_
```bash
```

_macOS_
```bash
```

### 获取EDK2源码
```bash
git clone https://github.com/tianocore/edk2.git
cd edk2
```

### 设置环境变量

_Windows_
```powershell
```

_Linux_
```bash
. edksetup.sh
```

_macOS_
```bash
```

尝试编译（探索EDK2系统）
```bash
build
```

### 修改编译目标
编辑Conf/target.txt，不同平台设置如下：

_Windows_
```powershell
```

_Linux_
```bash
ACTIVE_PLATFORM       = MdeModulePkg/MdeModulePkg.dsc
TOOL_CHAIN_TAG        = GCC5
```

_macOS_
```bash
```

另外，所有平台的共同设定：
```bash
 TARGET_ARCH           = X64
 ```

### 编译
```bash
build
```
成功后查看生成的文件及目录结构
```
find . -name "*.efi"
```

### 添加demo模块
```bash
mkdir demo
```

demo/demo.c:
```c

```

demo/demo.inf:
```inf

```

在MdeModulePkg/MdeModulePkg.dsc的[Components]段落末尾加上：
```
demo/demo.inf
```

最后，再次运行build，生成demo.efi

### 运行demo
想了个偷懒的办法，mount EFI分区，直接将demo.efi复制过去

_Windows_
```powershell
mountvol z: /s
cp -v demo.efi z:\EFI\
```

_Linux_
```bash
cp -v demo.efi /boot/efi/EFI/
```

_macOS_
```bash
diskutil mount /dev/disk0s1 # for example
cp -v demo.efi /Volumes/EFI/EFI/
```

然后重启机器，进入EFI/BIOS，选择EFI Shell
```bash
map # 查看EFI分区映射
fs0: # for example
cd EFI
demo.efi
```
