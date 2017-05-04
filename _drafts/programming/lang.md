[Home](/)

建议：脚本中#!一行建议尽量使用"#!/usr/bin/env X"的形式

## Regular Expressions

## 文件系统：文件与目录操作

### 需求
有如下文件，要求把“[]”及所包含的字符串删除
```
[电影天堂]111.rmvb
[盗版网站]22.mkv
...
```
### Bash
```
for fn in `ls`
do
  fm="${fn/\[*\]/}"
  if [ "$fm" != "$fn" ]; then
    mv -v "$fn" "$fm"
  fi
done
```

### PowerShell
```
foreach ($fn in Get-ChildItem) {
    $fn = $fn.Name
    $fm = $fn -replace "\[.*\]", ""
    if (!$fm.Equals($fn)) {
        echo "mv $fn $fm" # dummy mv
    }
}
```

## NATS

http://nats.io/about/

![demo](http://latex.codecogs.com/gif.latex?Fib(n)=\frac{\left(\phi^{n}-\gamma^{n}\right)}{\sqrt{5}})

[Home](/)
