---
layout:     post
title:      解决 argument list too long 错误
subtitle:   使用 linux 的管道
date:       2020-07-13
author:     Me
header-img: img/bg-unix-linux.png
catalog: true
tags:
    - Linux
    - Bash
---

## 命令

```sh
find . -name "*.ps" | xargs rm -rf "*.ps"
```

