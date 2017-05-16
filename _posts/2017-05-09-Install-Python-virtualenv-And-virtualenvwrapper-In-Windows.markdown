---
layout:     post
title:      "Windows下安装Python的虚拟环境virtualenv以及virtualenvwrapper"
subtitle:   ""
date:       2017-05-09
author:     "Tesla9527"
header-img: "img/home-bg-art.jpg"
catalog:    false
tags:
    - Python
---

原文地址：
[http://blog.csdn.net/shaququ/article/details/54292043](http://blog.csdn.net/shaququ/article/details/54292043)

virtualenv

1. 安装virtualenv

	pip install virtualenv
	

2. 新建虚拟环境

	virtualenv testvir
	
	注： 1. 虚拟环境位于当前命令的目录下 这里是 C:\
        2. 虚拟环境名称为 testvir
		
3. 进入虚拟环境
	
	1) 进入虚拟环境目录： cd C:\
	2) 进入脚本目录：     cd testvir\Scripts
	3) 运行activate.bat:  activate.bat
	
	
	查看虚拟环境中默认安装的库
	pip list
	
4. 虚拟环境下安装开发库， 这里以requests库为参考

	pip install request
	

5. 退出virtualenv

	deactivate.bat
	
virtualenvwrapper
上面每次进入virtual我们都需要进入到virtualenv的目录下，一旦virtualenv过多，就蛋疼了，接下来隆重推荐virtualenvwrapper
1. 安装virtualenvwrapper

	pip install virtualenvwrapper-win
	注： linux下运行pip install virtualenvwrapper
	
	设置WORK_HOME环境变量
	
2. 新建虚拟环境

	mkvirtualenv testvir
	
	注：因为前一步设置了WORK_HOME，所有虚拟环境将安装到 E:\python_virtual_env\testvir
	
3. 查看安装的所有虚拟环境
	workon
	
	