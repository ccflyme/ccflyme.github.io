---
layout:     post
title:      "JMeter – Building a Database Test Plan"
subtitle:   ""
date:       2016-08-11
author:     "Tesla9527"
header-img: "img/home-bg-art.jpg"
catalog:    false
tags:
    - JMeter
---

**操作视频：**

<iframe width="560" height="315" src="https://www.youtube.com/embed/qtTNW6ukLa4" frameborder="0" allowfullscreen></iframe>

---

**步骤解析：**

**1. Add Thread Group**
![img](/img/in-post/JMeter1.jpg)
我们添加了50个用户，准备时长为10秒，100个循环次数。并把Thread Group的名字改为了JDBC Users

**2. Add JDBC Connection Configuration**

为了完成Demo，我在本机装了MySQL，下图是安装之后的情况：
![img](/img/in-post/JMeter2.jpg)
其中的world是我们打算连接过去的数据库，数据库的server是localhost，用户名为root，密码是我们安装完MySQL之后自己输入的密码。
![img](/img/in-post/JMeter3.jpg)
参照上图，下面的一些字段是我们应该填的：

- Variable name：(here: myDatabase) bound to pool. This needs to uniquely identify the configuration. It is used by the JDBC Sampler to identify the configuration to be used。相当于是告诉我们的JSBC Sampler应该使用哪个JDBC Connection Configuration。

- Database URL: jdbc:mysql://localhost:3306/world(world是我们打算连接的数据库)

- JDBC Driver class: com.mysql.jdbc.Driver

- Username: the username of database(这里我们用的是root)

- Password: password for the username(安装MySQL时填写的密码)

**3. Add JDBC Request**
![img](/img/in-post/JMeter4.jpg)

- Pool Name: ‘myDatabase’ (same as in the configuration element)

**4. Add Listener**
![img](/img/in-post/JMeter4.jpg)
