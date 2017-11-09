---
layout:     post
title:      "使用Python和Selenium做Web自动化测试"
subtitle:   ""
date:       2017-11-09
author:     "Tesla9527"
header-img: "img/post-bg-alitrip.jpg"
catalog:    false
tags:
    - Python
---

原框架地址：
[https://github.com/Anthonyliu86/automation_framework_demo](https://github.com/Anthonyliu86/automation_framework_demo)

该框架已经很不错了，我稍微做了一些调整。
1. 调整了一下目录结构，这样在命令行中执行的时候，能将framework和pageobject中的模块成功导入而不出错。
2. 原框架将元素的uimap和操作方法都放在了pageobject中各自的page，我感觉还是放在单独地一个uimap文件夹中比较好，这样后期有元素变动或者其他页面也有使用该元素的需要时，能更加方便。
3. 在命令行中执行时，之前会出现log中element内容显示为空和乱码的情况，对该问题做了修复。
4. 原框架在执行完每一个case之后都会进行截图，这样对资源比较浪费，我修改为只在case fail的时候进行截图。
5. 原框架在使用HtmlTestRunner进行case的搜集和执行，并汇总所有case的执行结果到html报告中，我在报告中增加了一列ScreenShot，将fail的case的截图链接放在该列中。
