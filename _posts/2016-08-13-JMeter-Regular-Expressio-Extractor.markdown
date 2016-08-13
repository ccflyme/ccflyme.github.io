---
layout:     post
title:      "JMeter – Regular Expression Extractor"
subtitle:   ""
date:       2016-08-13
author:     "Tesla9527"
header-img: "img/home-bg-art.jpg"
catalog:    false
tags:
    - JMeter
---

正则表达式提取器可以提取出我们想要的变量值，比如说我们执行一连串CRUD的操作，我们先create了一条数据，之后我们需要对这条数据进行update和delete，就需要找到我们create的是哪一条数据。

![img](/img/in-post/JMeter26.jpg)

如上图所示，Regular Expression中括号()里面提取来的内容就是我们要的值，然后把这个值放到了Reference Name中，方便下面的请求中调用。
