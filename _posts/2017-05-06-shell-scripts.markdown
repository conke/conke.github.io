---
layout: post
title: "系统脚本（Bash/PowerShell）"
date: "2017-05-06 04:51:03 +0800"
---

<!-- 建议：脚本中#!一行建议尽量使用"#!/usr/bin/env X"的形式 -->

# 1. Regular Expressions

# 2. 文件系统：文件与目录操作

## 2.1. 需求
有如下文件，要求把“[]”及所包含的字符串删除
```
[电影天堂]111.rmvb
[盗版网站]22.mkv
...
```
## 2.2. Bash

```bash
for fn in `ls`; do
  fm="${fn/\[*\]/}"
  if [ "$fm" != "$fn" ]; then
    mv -v "$fn" "$fm"
  fi
done
```

## 2.3. PowerShell

```powershell
foreach ($fn in Get-ChildItem) {
    $fn = $fn.Name
    $fm = $fn -replace "\[.*\]", ""
    if (!$fm.Equals($fn)) {
        echo "mv $fn $fm" # dummy mv
    }
}
```

# 3. NATS

http://nats.io/about/

![demo](http://latex.codecogs.com/gif.latex?Fib(n)=\frac{\left(\phi^{n}-\gamma^{n}\right)}{\sqrt{5}})

# 4. 系统脚本应用示例

# 5. VMWare自动启动

## 5.1. 需求
Windows启动时自动打开某个路径下的所有vmware虚拟机。
注意，需要考虑到该路径下的虚拟机可能会发生变化（增删）

## 5.2. PowerShell脚本
vm-launch.ps1
```powershell
$vmdk = "d:\vmdk"

$args = @("-n", "-q", "-x", "")

foreach ($dir in Get-ChildItem $vmdk) {
    foreach ($vmx in Get-ChildItem $vmdk\$dir) {
       if ($vmx.Extension.Equals('.vmx')) {
           $args[-1] =  $vmx.FullName # "-n -q -x $vmx.FullName"
           & "C:\Program Files (x86)\VMware\VMware Workstation\vmware.exe" $args
           break
       }
    }
}
```

## 5.3. 自动启动
在regedit的run中新建一REG_SZ，值为"powershell -File \path\to\vm-launch.ps1"

# 6. 环境变量 (Windows)
for current login:
```powershell
[System.Environment]::SetEnvironmentVariable("A", "1", "User");
[System.Environment]::GetEnvironmentVariable("A", "User");
[System.Environment]::GetEnvironmentVariable("A", "Machine");
```

for all users (run as administrator):
```powershell
[System.Environment]::SetEnvironmentVariable("B", "2", "Machine");
[System.Environment]::GetEnvironmentVariable("B", "User");
[System.Environment]::GetEnvironmentVariable("B", "Machine");
```

## 6.1. genfstab for Gentoo
