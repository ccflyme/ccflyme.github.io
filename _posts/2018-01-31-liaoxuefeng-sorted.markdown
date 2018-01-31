---
layout:     post
title:      "廖雪峰python课后作业-使用sorted排序"
subtitle:   ""
date:       2018-01-31
author:     "Tesla9527"
header-img: "img/post-bg-alitrip.jpg"
catalog:    false
tags:
    - Python
---
```python
# 假设我们用一组tuple表示学生名字和成绩：
L = [('Bob', 75), ('Adam', 92), ('Bart', 66), ('Lisa', 88)]


# 请用sorted()对上述列表分别按名字排序：
def by_name(t):
    return t[0]


L2 = sorted(L, key=by_name)
print(L2)


# 再按成绩从高到低排序：
def by_score(t):
    return t[1]


L2 = sorted(L, key=by_score, reverse=True)
print(L2)
```
