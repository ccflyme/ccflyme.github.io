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
    - Vue.js
    - HTML
---
最近在学习js，在想怎么样把自己学的知识用一个项目全都融合一起。苦思良久，想到了之前学C#时候做的一个Online Shopping Store，觉得应该可以
把这个项目继续改造，这样就可以达到实战练习的目的了。

今天和Emcee聊了下，自己最近很疑惑，我们的项目前端页面是用纯html写的，那是怎么控制某个路由下面应该显示某个页面呢？MVC的话是用controller
来控制的。原来是用AngularJS的前端路由来控制的。

新建了一个MVC的模板网站，在里面怎么都没有找到在哪里定义的Entity。Anyway，从数据的流转来看，应该都是先从数据库中读取数据，然后将值
绑定在Model上，通过Model上的值来做数据展示或相应的判断。

自己大致规划了一下，功能点如下：

	1. 注册登录
	2. 个人中心
	3. 浏览商品
	4. 加入购物车
	5. 购买
	6. 发送邮件通知

其中UI，可以使用Vue.js实现的一套UI，逻辑代码使用C#。这样就做到了从前台到后台的整合。

---
项目命名：Tesla.EShop

先实现注册登录，个人中心。（已实现，目前需要弄清楚Entity和Model之间的关系）

晚上请教了一下徐瑞，了解到Entity是和数据库中的Table对应，Model其实是ViewModel，相当于Dto，和页面上的字段对应。还需要研究一下EntityFramework中的DbContext到底应该要怎么样设置，因为MVC模板中已经有一个DbContext了，这2个怎么整合到一起。自己之前想的用一个工程来专门配置EntityFramework，看来没有必要，直接配置在Model的Project中就可以了。

今晚再次向徐瑞请教，通过继承完美地配置好了DbContext。也觉得MVC无论是从代码的分层设计，还是从大的角度来看，都是非常精准的。我们处理的是数据，用Model来代表，无论数据存放在什么数据库里面，另外就是Controller，通过路由指向数据的处理逻辑，最后是View，数据经过处理之后展现在用户面前。
