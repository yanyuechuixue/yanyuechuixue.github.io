---
layout:     post
title:      Oracle Cloud Ubuntu 装 宝塔以后 no route to host 的解决办法
subtitle:   把 UFW 删掉, 用 firewalld 打开端口
date:       2020-07-29
author:     Me
header-img: img/bg-unix-linux.png
catalog: true
tags:
    - Oracle
    - Ubuntu
    - 宝塔
    - UFW
---

卸载 ufw , 恢复路由表

```bash
sudo apt remove ufw
sudo iptables-restore < /etc/iptables/rules.v4
```



## 安装 firewalld，并开放端口

```sh
sudo apt install firewalld
sudo firewall-cmd  --permanent --zone=public --add-port=80/tcp
sudo firewall-cmd  --permanent --zone=public --add-port=443/tcp
sudo firewall-cmd  --reload
```

