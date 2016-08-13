---
layout:     post
title:      "JMeter – Building a Monitor Test Plan"
subtitle:   ""
date:       2016-08-13
author:     "Tesla9527"
header-img: "img/home-bg-art.jpg"
catalog:    false
tags:
    - JMeter
---

**操作视频：**

<iframe width="560" height="315" src="https://www.youtube.com/embed/d9DnE-U8J24" frameborder="0" allowfullscreen></iframe>

---

**步骤解析：**

这里对于Server的Monitor我采用的是[http://jmeter-plugins.org/](http://jmeter-plugins.org/)里面的插件，挺好用的。

1. 双击下载完的ServerAgent中的startAgent.bat，这样可以让我们的插件能够监控到相应Server的数据。

    ![img](/img/in-post/JMeter23.jpg)

    ![img](/img/in-post/JMeter24.jpg)

2. 打开或新建一个Test Plan，然后添加jp@gc – PerfMon Metrics Collector。我这里是用的是一个Web Service的Test Plan，ServerAgent是在我本地启动的，所以监控到的是我本地的数据。实际测试的时候我们想监控哪个Server，我们就在哪个Server上启动ServerAgent就可以了。

    ![img](/img/in-post/JMeter25.jpg)
