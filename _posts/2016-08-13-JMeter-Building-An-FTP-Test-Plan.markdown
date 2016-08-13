---
layout:     post
title:      "JMeter – Building an FTP Test Plan"
subtitle:   ""
date:       2016-08-13
author:     "Tesla9527"
header-img: "img/home-bg-art.jpg"
catalog:    false
tags:
    - JMeter
---

**操作视频：**

<iframe width="560" height="315" src="https://www.youtube.com/embed/Ud5kdDZMTDE" frameborder="0" allowfullscreen></iframe>

---

**步骤解析：**

**1. Add Thread Group**

为了完成FTP的测试，我们首先要有一台FTP Server，这里我们可以自己在本机安装一个，让自己的本机变成FTP Server，就可以了。
我们用[http://www.goldenftpserver.com/](http://www.goldenftpserver.com/)就可以了，安装完成后，我们添加一个目录用来存放FTP Server中的文件，如下图：
![img](/img/in-post/JMeter6.jpg)

**2. Add Thread Group**
![img](/img/in-post/JMeter7.jpg)

**3. Add FTP Request Defaults**
![img](/img/in-post/JMeter8.jpg)

**4. Add FTP Request**

我们先添加一个Get请求,

Remote File: /FTPServer/test1.jpg

Local File: C:/Users/Lin/Desktop/Local/test1.jpg

Login Configuration

Username: anonymous

Password: anonymous

![img](/img/in-post/JMeter9.jpg)

再添加一个Put请求

Remote File: /FTPServer/test2.txt

Local File: C:/Users/Lin/Desktop/Local/test2.txt

Login Configuration

Username: anonymous

Password: anonymous

![img](/img/in-post/JMeter10.jpg)

**4. Add Listener**

![img](/img/in-post/JMeter11.jpg)
