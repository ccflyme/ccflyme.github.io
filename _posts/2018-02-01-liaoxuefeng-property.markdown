---
layout:     post
title:      "廖雪峰python课后作业-使用@property"
subtitle:   ""
date:       2018-02-01
author:     "Tesla9527"
header-img: "img/post-bg-alitrip.jpg"
catalog:    false
tags:
    - Python
---
```python
# 请利用@property给一个Screen对象加上width和height属性，以及一个只读属性resolution：
class Screen(object):
    @property
    def width(self):
        return self._width  # 加下划线是为了避免程序员混乱，是调属性，还是调方法（就算不加下划线，编译器也会避免递归）

    @width.setter
    def width(self, value):
        if value <= 0:
            raise ValueError()
        self._width = value

    @property
    def height(self):
        return self._height

    @height.setter
    def height(self, value):
        if value <= 0:
            raise ValueError()
        self._height = value

    @property
    def resolution(self):
        try:
            return self._width * self._height
        except AttributeError:
            return 0


# 测试:
s = Screen()
s.width = 1024
s.height = 768
print('resolution =', s.resolution)
if s.resolution == 786432:
    print('测试通过!')
else:
    print('测试失败!')
```
