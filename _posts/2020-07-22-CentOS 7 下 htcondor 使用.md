---
layout:     post
title:      CentOS 7 下 htcondor 使用
subtitle:   暴力方法
date:       2020-07-22
author:     Me
header-img: img/bg-unix-linux.png
catalog: true
tags:
    - CentOS
    - condor
    - htcondor
	  - selinux
---

安装并不困难

```bash
sudo yum install condor
```



## 暴力关闭selinux

```sh
sudo setenforce 0
```

