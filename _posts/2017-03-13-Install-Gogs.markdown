---
layout:     post
title:      "安装Gogs"
subtitle:   ""
date:       2017-03-13
author:     "Tesla9527"
header-img: "img/gogs.jpg"
catalog:    true
tags:
    - Gogs
    - Git
---
>现在部署使用Git服务器的工具挺多的，比如果Gitlab，Gogs，Bonobo等等。目前我没有搭建Linxu虚拟机，对Linux也不是很熟悉，就用Gogs在Windows上搭建一下。

环境
1. Windows OS
2. MSSQL
3. Git For Windows
4. Gogs

安装步骤
## 新建Gogs空数据库
Gogs支持的数据库挺多的，由于是在Windows上操作，我就用MSSQL了。
![img](/img/in-post/gogs1.jpg)

## 安装Gogs
在Gogs官网上找到二进制安装下载，解压到某个路径下。
![img](/img/in-post/gogs2.jpg)
执行.\gogs.exe web
![img](/img/in-post/gogs3.jpg)






