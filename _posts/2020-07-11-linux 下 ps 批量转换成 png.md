---
layout:     post
title:      linux 下 ps 批量转换成 png
subtitle:   图片格式转换
date:       2020-07-11
author:     Me
header-img: img/bg-unix-linux.png
catalog: true
tags:
    - Linux
    - Bash
    - Plot
---

## 安装

从 http://www.imagemagick.org/script/download.php 下载安装包并安装.

## 脚本

```sh
#!/bin/sh

########################
## using “convert” from ImageMagick to do ps convert into PNG
#########################

echo PS convert to PNG, please wait the process
for INP in *.ps
do
newname=`basename $INP .ps`
convert -density 150 -geometry 100% $INP $newname%02d.png
echo ” convert $INP to $newname.png completely”
done
echo ” process ended, please check your graphical files”
```





---

参考了

https://kpwu.wordpress.com/2006/01/26/conver-all-ps-to-png-format-by-a-script/

