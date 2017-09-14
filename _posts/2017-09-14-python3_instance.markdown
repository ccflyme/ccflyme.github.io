---
layout:     post
title:      "python例子"
subtitle:   ""
date:       2017-09-14
author:     "Tesla9527"
header-img: "img/post-bg-alitrip.jpg"
catalog:    false
tags:
    - Python
---

原文地址：
[http://www.runoob.com/python3/python3-examples.html](http://www.runoob.com/python3/python3-examples.html)

Python Hello World 实例
```python
# -*- coding: UTF-8 -*-

# Filename : helloworld.py
# author by : www.runoob.com

# 该实例输出 Hello World!
print('Hello World!')
```
Python 数字求和
```python
# -*- coding: UTF-8 -*-

# Filename : test.py
# author by : www.runoob.com

# 用户输入数字
num1 = input('输入第一个数字：')
num2 = input('输入第二个数字：')

# 求和
sum = float(num1) + float(num2)

# 显示计算结果
print('数字 {0} 和 {1} 相加结果为： {2}'.format(num1, num2, sum))
```
Python 平方根
```python
# -*- coding: UTF-8 -*-
 
# Filename : test.py
# author by : www.runoob.com
 
num = float(input('请输入一个数字： '))
num_sqrt = num ** 0.5
print(' %0.3f 的平方根为 %0.3f'%(num ,num_sqrt))
```
