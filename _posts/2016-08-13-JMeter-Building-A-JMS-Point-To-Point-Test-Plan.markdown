---
layout:     post
title:      "JMeter – Building a JMS Point to point Test Plan"
subtitle:   ""
date:       2016-08-13
author:     "Tesla9527"
header-img: "img/home-bg-art.jpg"
catalog:    false
tags:
    - JMeter
---

**操作视频：**

<iframe width="560" height="315" src="https://www.youtube.com/embed/GEFonZ3zjC4" frameborder="0" allowfullscreen></iframe>

---

**步骤解析：**


1. 针对JMS类型的Sampler，需要额外的jar包（这里将下载的AMQ apache-activemq-5.11.1根目录下的activemq-all-5.11.1.jar拷贝到JMETER_HOME\lib目录下）

2. 启动ActiveMQ：打开dos窗口，进入ActiveMQ解压目录下的bin目录，输入命令：activemq.bat start

3. Add Thread Group

4. Add JMS Point-to-Point Sampler

    ![img](/img/in-post/JMeter17.jpg)

    ![img](/img/in-post/JMeter18.jpg)

    填入如下字段：

    QueueConnection Factory： ConnectionFactory

    JNDI name Request queue：Q.REQ

    JNDI name Recieve queue：Q.REQ

    Communication style：Request only或者Request Response都行

    Use Request Message Id: Checked

    Use Response Message Id: Checked

    Timeout(ms): 2000

    Content: Testing point to point

    Initial Context Factory：org.apache.activemq.jndi.ActiveMQInitialContextFactory

    JNDI Properties:

    Name: queue.Q.REQ    Value: example.A

    Provider URL: tcp://localhost:61616

5. Add View Results Tree
