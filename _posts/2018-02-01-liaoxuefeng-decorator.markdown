---
layout:     post
title:      "廖雪峰python课后作业-装饰器"
subtitle:   ""
date:       2018-02-01
author:     "Tesla9527"
header-img: "img/post-bg-alitrip.jpg"
catalog:    false
tags:
    - Python
---
```python
# 请设计一个decorator，它可作用于任何函数上，并打印该函数的执行时间：
import time
import functools


def metric(fn):
    @functools.wraps(fn)
    def wrapper(*args, **kwargs):
        print('begin call')
        time_begin = time.clock()
        result = fn(*args, **kwargs)
        print('end call')
        time_end = time.clock()
        print('%s executed in %s ms' % (fn.__name__, time_end - time_begin))
        return result

    return wrapper


# 测试
@metric
def fast(x, y):
    time.sleep(0.0012)
    print('I am fast')
    return x + y


@metric
def slow(x, y, z):
    time.sleep(0.1234)
    print('I am slow')
    return x * y * z


f = fast(11, 22)
s = slow(11, 22, 33)
if f != 33:
    print('测试失败!')
elif s != 7986:
    print('测试失败!')

```
