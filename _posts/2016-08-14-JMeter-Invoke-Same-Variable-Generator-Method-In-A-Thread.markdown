---
layout:     post
title:      "JMeter – 同一个线程组中每个线程调用相同的变量生成函数"
subtitle:   ""
date:       2016-08-13
author:     "Tesla9527"
header-img: "img/home-bg-art.jpg"
catalog:    false
tags:
    - JMeter
---

自己之前弄了个用户自定义变量，然后在线程组中调用，结果执行的时候是先把这个变量生成，然后每个线程再去调用。后来折腾了一段时间之后，把这个变量生成的函数直接放在需要使用的地方，然后每个线程就会在各自执行的时候去生成值，不需要先定义再调用。

![img](/img/in-post/JMeter28.jpg)
