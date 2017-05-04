

### 5.1. 版本选择

#### 5.1.1. Python

考虑一：基本工具（pip & venv）的支持

version | source | pip | 语言内建venv | 结论 = pip \| venv
--------|--------|-----|-------------|----
2.6 | Base | T, [但已经deprecated](/programming/build) | F | F
2.7 | IUS | T | F | T
3.4 | EPEL | F | T, 但"--without-pip" | 需要手动get-pip
3.4 | IUS | T | T | T
3.5 | IUS | T | T | T
3.6 | IUS | F | T | T

看来CentOS6(Base+EPEL)对Python的支持并不好。

考虑二：对uWSGI和mod_wsgi的支持

version | source | uWSGI | mod_wsgi | 结论 = uWSGI & mod_wsgi
--------|--------|-------|----------|-----
2.7 | IUS | T | T | T
3.4 | EPEL | F | F | F
3.4 | IUS | T | F | F
3.5 | IUS | T | T | T
3.6 | IUS | F | F | F

——花了一个上午，突然发现表一（考虑一）基本是多余的！:sob:
<!--不过没有删除仍保留着，是考虑到这样的工作方式和思路可能对你有参考和帮助。-->

剩下2.7和3.5