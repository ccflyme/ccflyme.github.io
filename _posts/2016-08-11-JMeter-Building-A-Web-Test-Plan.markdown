---
layout:     post
title:      "JMeter – Building a Web Test Plan"
subtitle:   ""
date:       2016-08-11
author:     "Tesla9527"
header-img: "img/home-bg-art.jpg"
catalog:    false
tags:
    - JMeter
---

最近找JMeter的学习资料，发现链接[http://www.javacodegeeks.com/2014/11/jmeter-tutorial-load-testing.htm](http://www.javacodegeeks.com/2014/11/jmeter-tutorial-load-testing.htm)
中的文章对于JMeter入门很不错，于是我就按照里面的例子一个一个进行模拟，并把操作步骤录制了下来。

<iframe width="560" height="315" src="https://www.youtube.com/embed/unjOY76RVms?list=PLStEBKEmr3Z-xN3pJ9vxWXvUors-gm0lP" frameborder="0" allowfullscreen></iframe>

---

**操作步骤分析：**

- Add Tread Group

  - 线程数：5    虚拟用户数，一个虚拟用户占用一个线程，这里相当于是模拟了5个虚拟用户

  - 准备时长（Ramp-Up Period(in seconds)：1    设置的虚拟用户数需要多长时间全部启动。如果线程数为5 ，准备时长为1 ，那么需要1秒钟启动5个线程。也就是每200ms启动1个线程

  - 循环次数（Loop Count）：7    每个线程发送请求的次数。如果线程数为5，循环次数为7 ，那么每个线程发送7次请求。总请求数为5*7=35 。如果勾选了“永远”，那么所有线程会一直发送请求，一到选择停止运行脚本。

- Add Sampler -> HTTP Request

  - 在Server Name中填入www.baidu.com,用来向baidu发送请求

- Add Listen -> View Result Tree

  - 通过添加监听器来获得测试结果
