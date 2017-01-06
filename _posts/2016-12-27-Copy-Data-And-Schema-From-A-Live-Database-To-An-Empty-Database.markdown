---
layout:     post
title:      "从一个正在使用的Sql Server数据库复制Schema和Data到一个空的库"
subtitle:   ""
date:       2016-12-27
author:     "Tesla9527"
header-img: "img/home-bg-art.jpg"
catalog:    false
tags:
    - MS SQL Server
---
Sql Server数据库的log文件增长的太快了，今天准备还原正在开发的库到阿里云上，发现ldf文件已经有45.5G了，完全没有空间去还原，也想过直接删掉log文件，但是没有成功。

后来用Visual Studio的Schema Compare和SSMS的Import Data解决了这个问题。

1. 新建一个新的空库
2. 使用Visual Studio的Schema Compare来对比原始库和新库，update之后会将原始库的Schema，PK，Index，Procedure，Function等等全都复制到新库上
3. 使用SSMS的Import Data从原始库导入数据到新库

再后来找到一个比较简便的方法
<iframe width="560" height="315" src="https://www.youtube.com/embed/9OGrtiZcCa8" frameborder="0" allowfullscreen></iframe>
