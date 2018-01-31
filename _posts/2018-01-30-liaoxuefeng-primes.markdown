---
layout:     post
title:      "廖雪峰python课后作业-打印n以内的素数，打印回数"
subtitle:   ""
date:       2018-01-30
author:     "Tesla9527"
header-img: "img/post-bg-alitrip.jpg"
catalog:    false
tags:
    - Python
---
打印n以内的素数：方法一
```python
# 构造一个从3开始的奇数序列
def _odd_iter():
    x = 1
    while True:
        x = x + 2
        yield x


# 定义一个筛选函数
def _not_divisible(y):
    return lambda x: x % y > 0


# 定义一个生成器，不断返回下一个素数
def primes():
    yield 2
    it = _odd_iter()  # 初始序列
    while True:
        z = next(it)  # 返回序列的第一个数
        yield z
        it = filter(_not_divisible(z), it)  # 构造新序列


for n in primes():
    if n < 100000:
        print(n)
    else:
        break
```
打印n以内的素数：方法二
```python
import math


def func_get_prime(n):
    return filter(lambda x: not [x % i for i in range(2, int(math.sqrt(x)) + 1) if x % i == 0], range(2, n + 1))

print(list(func_get_prime(10000)))
```
打印回数：
```python
def is_palindrome(n):
    return str(n)[::-1] == str(n)


output = filter(is_palindrome, range(1, 1000))
print('1~1000:', list(output))
if list(filter(is_palindrome, range(1, 200))) == [1, 2, 3, 4, 5, 6, 7, 8, 9, 11, 22, 33, 44, 55, 66, 77, 88, 99, 101,
                                                  111, 121, 131, 141, 151, 161, 171, 181, 191]:
    print('测试成功!')
else:
    print('测试失败!')
```
