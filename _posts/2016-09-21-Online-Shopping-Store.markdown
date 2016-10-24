---
layout:     post
title:      "Online Shopping Store项目实战练习"
subtitle:   ""
date:       2016-09-21
author:     "Tesla9527"
header-img: "img/home-bg-art.jpg"
catalog:    false
tags:
    - C#
    - React
    - JS
    - HTML
---
最近在学习js，在想怎么样把自己学的知识用一个项目全都融合一起。苦思良久，想到了之前学C#时候做的一个Online Shopping Store，觉得应该可以
把这个项目继续改造，这样就可以达到实战练习的目的了。

今天和Emcee聊了下，自己最近很疑惑，我们的项目前端页面是用纯html写的，那是怎么控制某个路由下面应该显示某个页面呢？MVC的话是用controller
来控制的。原来是用AngularJS的前端路由来控制的。

自己大致规划了一下，功能点如下：

	1. 注册登录
	2. 个人中心
	3. 浏览商品
	4. 加入购物车
	5. 购买
	6. 发送邮件通知

其中UI，可以使用蚂蚁金服使用React实现的一套UI，交互上使用JS，逻辑代码使用C#。这样就做到了从前台到后台的整合。

---
项目命名：Tesla.EShop

先实现注册登录，个人中心。
