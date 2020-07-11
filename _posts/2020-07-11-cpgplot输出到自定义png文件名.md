---
layout:     post
title:      cpgplot输出到png文件
subtitle:   以及如何输出到指定的文件名
date:       2020-07-11
author:     Me
header-img: img/bg-unix-linux.png
catalog: true
tags:
    - iOS
    - CocoaPods
    - Git
---



## 语法

```c++
if ( (newgraph == 1) || (newgraph == 3) ) {
    if (device == 0x0) device = "?" ;    
	  int ier = cpgbeg(0, device, nxpage, nypage) ;
	  if (ier != 1) {
	      cout << "problem in opening PGPLOT display !" << endl ;
	  }
}
```



## 可用的device list

```
Graphics device/type (? to see list, default /Xserve): ?
PGPLOT v5.2.2 Copyright 1997 California Institute of Technology
Interactive devices:
   /XWINDOW   (X window window@node:display.screen/xw)
   /XSERVE    (A /XWINDOW window that persists for re-use)
Non-interactive file formats:
   /GIF       (Graphics Interchange Format file, landscape orientation)
   /VGIF      (Graphics Interchange Format file, portrait orientation)
   /LATEX     (LaTeX picture environment)
   /NULL      (Null device, no output)
   /PNG       (Portable Network Graphics file)
   /TPNG      (Portable Network Graphics file - transparent background)
   /PS        (PostScript file, landscape orientation)
   /VPS       (PostScript file, portrait orientation)
   /CPS       (Colour PostScript file, landscape orientation)
   /VCPS      (Colour PostScript file, portrait orientation)
Graphics device/type (? to see list, default /Xserve):
```

## 如果设置为 /PNG 

```c++
int ier = cpgbeg(0, '/PNG', nxpage, nypage) ;
```

会在执行目录输出成 `pgplot.png`.

## 自定义文件名

```c++
int ier = cpgbeg(0, 'mypic.png/PNG', nxpage, nypage) ;
```



----

参考了 https://www.aber.ac.uk/en/media/departmental/imaps/pdfs/laboratoryfiles/ws_ph30610_pgplot.pdf

