---
layout:     post
title:      "JMeter – Building a JMS Topic Test Plan"
subtitle:   ""
date:       2016-08-13
author:     "Tesla9527"
header-img: "img/home-bg-art.jpg"
catalog:    false
tags:
    - JMeter
---

**操作视频：**

<iframe width="560" height="315" src="https://www.youtube.com/embed/YqGQJ8rHnrA" frameborder="0" allowfullscreen></iframe>

---

**步骤解析：**

**1. Add Thread Group**

![img](/img/in-post/JMeter19.jpg)

**2. Add JMS Publisher**
![img](/img/in-post/JMeter20.jpg)

>特别注意：这里有一个很坑的地方，就是Expiration(ms)和Period(0-9)一定要填值，要不然就会报错！

**3. Add JMS Subscriber**

![img](/img/in-post/JMeter21.jpg)

**4. Add View Results Tree**

![img](/img/in-post/JMeter22.jpg)
