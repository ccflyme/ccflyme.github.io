---
layout:     post
title:      "廖雪峰python课后作业-返回函数以及闭包"
subtitle:   ""
date:       2018-01-31
author:     "Tesla9527"
header-img: "img/post-bg-alitrip.jpg"
catalog:    false
tags:
    - Python
---
```python
# 利用闭包返回一个计数器函数，每次调用它返回递增整数
def create_counter():
    a = [0]

    def counter():
        a[0] = a[0] + 1
        return a[0]

    return counter


counterA = create_counter()
print(counterA(), counterA(), counterA(), counterA(), counterA())  # 1 2 3 4 5
counterB = create_counter()
if [counterB(), counterB(), counterB(), counterB()] == [1, 2, 3, 4]:
    print('测试通过!')
else:
    print('测试失败!')
```
