---
layout:     post
title:      "接口测试"
subtitle:   ""
date:       2017-02-26
author:     "Tesla9527"
header-img: "img/home-bg-art.jpg"
catalog:    false
tags:
    - 接口测试
    - Python
---
>接口测试的目的：项目开发中，接口一般比较早的做好，QA能在UI出现之前对接口进行测试，是对质量比较好的控制。

什么是接口测试？（以下引用云层天资中云层老师的讲解）

	1.接口是指系统模块与模块或系统与系统间进行交互，一般我们用的多是Http协议的接口，WebService协议的接口，还有RPC（Remote Procedure Call Protocal远程过程调用协议的接口）。

	2.不管是哪种接口，其本质就是发送一个request，然后服务器响应后返回一个response，然后我们对response进行分析，这就是接口测试。

这段时间在新公司里，参考老大的框架，使用Python把接口测试做完了。其中urllib模块被我换成了requests模块，使用起来会更加方便一点。在文件夹中的__init__.py文件中也去掉了路径的设置，留了
一个空文件，但是却能确保该文件夹下的模块能方便的被其他地方引用。

代码链接：
[https://github.com/Tesla9527/InterfaceTesting](https://github.com/Tesla9527/InterfaceTesting)


集成Jenkins：

接口测试一定要集成CI才能更好的发挥效果，集成起来比较简单，直接通过命令行调用就可以了。

	python your_dir\test_runner.py

Jenkins中发布测试报告：

	我们在接口测试中使用的是xmlrunner，会生成xml的report。在Jenkins中Post-build Actions，选用Publish JUnit test result report。 Test Report XMLs配置为reports/report*.xml

