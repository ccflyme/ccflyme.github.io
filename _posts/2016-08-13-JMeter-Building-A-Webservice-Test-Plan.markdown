---
layout:     post
title:      "JMeter – Building a Webservice Test Plan"
subtitle:   ""
date:       2016-08-13
author:     "Tesla9527"
header-img: "img/home-bg-art.jpg"
catalog:    false
tags:
    - JMeter
---

**操作视频：**

<iframe width="560" height="315" src="https://www.youtube.com/embed/OXz4svezH08" frameborder="0" allowfullscreen></iframe>

---

**步骤解析：**

我们这里测试的web service是[http://www.webxml.com.cn/WebServices/WeatherWebService.asmx?op=getSupportCity](http://www.webxml.com.cn/WebServices/WeatherWebService.asmx?op=getSupportCity)

**1. 新建Thread Group**

![img](/img/in-post/JMeter12.jpg)

**2. 新建HTTP Header Manager**
![img](/img/in-post/JMeter13.jpg)

填入如下内容：   

Name:  Content-Type

Value: text/xml; charset=utf-8

**3. 新建SOAP/XML-RPC Request**
![img](/img/in-post/JMeter14.jpg)

所填内容如下：

URL：http://www.webxml.com.cn/WebServices/WeatherWebService.asmx

Send SOAPAction勾选上，并填入内容http://WebXml.com.cn/getSupportCity

Soap/XML-RPC Data:

```
<soap:Envelope xmlns:xsi=”http://www.w3.org/2001/XMLSchema-instance; xmlns:xsd=”http://www.w3.org/2001/XMLSchema; xmlns:soap=”http://schemas.xmlsoap.org/soap/envelope/”;
  <soap:Body>
    <getSupportCity xmlns=”http://WebXml.com.cn/”;
      <byProvinceName>湖北</byProvinceName>
    </getSupportCity>
  </soap:Body>
</soap:Envelope>
```

**4. 新建Response Assertion**

![img](/img/in-post/JMeter15.jpg)

**4. 新建View Results Tree**

![img](/img/in-post/JMeter16.jpg)
