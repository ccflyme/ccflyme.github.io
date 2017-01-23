---
layout:     post
title:      "使用Octopus做持续部署"
subtitle:   ""
date:       2017-01-11
author:     "Tesla9527"
header-img: "img/home-bg-art.jpg"
catalog:    false
tags:
    - Octopus
---

>在使用TeamCity做完开发过程中的持续集成后，在部署的时候发现很多动作都是重复的，就想是不是也可以自动化掉。后来遇到了Octopus，感觉恰好可以解决这个问题。

2017-01-11，在测试环境安装完Octopus之后，用安装过程中配置的域账号登陆，一直没有Dashboard，提示没有权限，按照教程强行更新设置账号为管理员，还是不行。
后来在我本地安装的时候，使用local账号，结果可以看到Dashboard。至于之前使用域账号为什么不行，已经给官方发了邮件，等待回复中。

2017-01-23，VS中在想要发布的工程下添加OctoPack，执行下面的命令后成功地生成了nuget包，并且用NeGet Package Explorer成功打开。
msbuild E:\Yooya\Sl.Bpm\Bpm.Hmgd.Com-branch\Bpm.Hmgd.Com.sln /t:Build /p:RunOctoPack=true

一般来说，和采用publish方式生成的文件一样，但是我们这个工程有点特殊，需要将cs文件也当成和html、js一样的文件发布出来。所以在cs文件的属性中，将Build Action改
为Content就解决了这个问题。
修改前：
![img](/img/in-post/Octopus1.jpg)
修改后：
![img](/img/in-post/Octopus2.jpg)
