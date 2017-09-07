---
layout:     post
title:      "export dict/list to csv in python(转载)"
subtitle:   ""
date:       2017-09-07
author:     "Tesla9527"
header-img: "img/post-bg-alitrip.jpg"
catalog:    false
tags:
    - Python
---

原文地址：
[http://www.idiotinside.com/2015/04/14/export-dict-to-csv-list-to-csv-in-python/](http://www.idiotinside.com/2015/04/14/export-dict-to-csv-list-to-csv-in-python/)

需要注意的是，要想输出的csv不要每行数据之后都换一行，需要在DictWriter的参数中加如下2个delimiter=',', lineterminator='\n'
writer = csv.DictWriter(csvfile, fieldnames=fieldnames, delimiter=',', lineterminator='\n')
