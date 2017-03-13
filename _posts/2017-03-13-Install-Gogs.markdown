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

材料准备
	Windows OS
	MSSQL
	Git For Windows
	Gogs

安装步骤
## 安装Git For Windows
按照Git官网上教程完成安装。

## 新建Gogs空数据库
Gogs支持的数据库挺多的，由于是在Windows上操作，我就用MSSQL了。
![img](/img/in-post/gogs1.jpg)

## 安装Gogs
在Gogs官网上找到二进制安装下载，解压到某个路径下。
![img](/img/in-post/gogs2.jpg)
执行.\gogs.exe web
![img](/img/in-post/gogs3.jpg)
成功启动后，可以在gogs目录下建立了custom/conf/app.ini,这个config文件。
进入http://127.0.0.1:3000配置页面，按照官网说明完成配置。

## 设定Windows Service
Gogs官网上介绍了2中方法，Use Builtin Functionality以及Use NSSM。个人喜欢Use NSSM，因为简单方便。
安装完成后就可以通过Windows Service来开启或关闭Gogs了，方便维护。
![img](/img/in-post/gogs4.jpg)

## 操作界面预览
![img](/img/in-post/gogs5.gif)








