---
layout:     post
title:      "卸载Sql Server之后的悲剧"
subtitle:   ""
date:       2016-07-13
author:     "Tesla9527"
header-img: "img/home-bg-o.jpg"
catalog:    false
tags:
    - 工作
---
今天发现自己的C盘空间只剩下3G，直接彪红了。于是去查到底是什么占用了这么大的空间，后来发现Sql Server占了很大的空间，于是自己作死，进去把mdf文件和ldf文件
全部删除了，然后悲剧发生了。

已经存在的几个数据库一直处于Pending Recovering的状态，删也删不掉。想着直接把Sql Server卸载然后重装吧，于是去程序中把和Sql Server相关的全部卸载掉了，
Program Files中Sql Server相关的再全部手动删除，注册表中的信息全部删掉。重装之后，发现Sql Server的服务起不来，本地的Sql Server实例一直连不上。要么就是安装的时候提示component下面的一直GUID的Key没有读取权限，权限设置好之后，还是没有完美安装。

感觉Sql Server卸载之后就是一团乱麻，想要再次重新安装总是会出一些莫名其妙的问题。整体所花的时间还不如重装系统，再重装Sql Server。因为就算采用不重装系统的
方式重装Sql Server成功了，整体所花的时间还是不少，而且就算这样成功了，也证明不了什么，说不定是Microsoft本身对Sql Server的这一块没做好，没必要自己花那么
多时间去为他们的这种设计买单。

另外Sql Server的向下兼容不是很好，本来打算尝尝Sql Server 2016的鲜，但是如果是Sql Server 2016的数据库备份，用2014的版本是还原不了的。所以还是老老实实地直接
在装完系统之后重装Sql Server 2014吧。

下次重装系统，一定记得把C盘空间给大一点，200G吧。因为现在自己习惯安装软件的时候，默认都给装在C盘了。

删除Sql Server相关的注册表：
![img](/img/in-post/Delete-SqlRelated-Regedit.jpg)

安装Sql Server过程中报的错误：
![img](/img/in-post/SqlServer-Installation_Issue-One.jpg)

![img](/img/in-post/SqlServer-Installation_Issue-Two.jpg)
