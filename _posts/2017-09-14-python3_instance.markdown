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
Python 二次方程
```python
# Filename : test.py
# author by : www.runoob.com

# 二次方程式 ax**2 + bx + c = 0
# a、b、c 用户提供

# 导入 cmath(复杂数学运算) 模块
import cmath

a = float(input('输入 a: '))
b = float(input('输入 b: '))
c = float(input('输入 c: '))

# 计算
d = (b ** 2) - (4 * a * c)

# 两种求解方式
sol1 = (-b - cmath.sqrt(d)) / (2 * a)
sol2 = (-b + cmath.sqrt(d)) / (2 * a)

print('结果为 {0} 和 {1}'.format(sol1, sol2))
```
Python 计算三角形的面积
```python
# -*- coding: UTF-8 -*-

# Filename : test.py
# author by : www.runoob.com


a = float(input('输入三角形第一边长: '))
b = float(input('输入三角形第二边长: '))
c = float(input('输入三角形第三边长: '))

# 计算半周长
s = (a + b + c) / 2

# 计算面积
area = (s*(s-a)*(s-b)*(s-c)) ** 0.5
print('三角形面积为 %0.2f' %area)
```
Python 随机数生成
```python
# -*- coding: UTF-8 -*-

# Filename : test.py
# author by : www.runoob.com

# 生成 0 ~ 9 之间的随机数

# 导入 random(随机数) 模块
import random

print(random.randint(0,9))
```
Python 摄氏温度转华氏温度
```python
# -*- coding: UTF-8 -*-

# Filename : test.py
# author by : www.runoob.com

# 用户输入摄氏温度

# 接收用户收入
celsius = float(input('输入摄氏温度: '))

# 计算华氏温度
fahrenheit = (celsius * 1.8) + 32
print('%0.1f 摄氏温度转为华氏温度为 %0.1f ' %(celsius,fahrenheit))
```
Python 交换变量
```python
# -*- coding: UTF-8 -*-

# Filename : test.py
# author by : www.runoob.com

# 用户输入

x = input('输入 x 值: ')
y = input('输入 y 值: ')

# 不使用临时变量
x, y = y, x

print('交换后 x 的值为: {}'.format(x))
print('交换后 y 的值为: {}'.format(y))
```
Python if 语句
```python
# -*- coding: UTF-8 -*-

# Filename : test.py
# author by : www.runoob.com

# 用户输入数字

num = float(input("输入一个数字: "))
if num > 0:
    print("正数")
elif num == 0:
    print("零")
else:
    print("负数")
```
Python 判断字符串是否为数字
```python
# -*- coding: UTF-8 -*-

# Filename : test.py
# author by : www.runoob.com

def is_number(s):
    try:
        float(s)
        return True
    except ValueError:
        pass

    try:
        import unicodedata
        unicodedata.numeric(s)
        return True
    except (TypeError, ValueError):
        pass

    return False


# 测试字符串和数字
print(is_number('foo'))  # False
print(is_number('1'))  # True
print(is_number('1.3'))  # True
print(is_number('-1.37'))  # True
print(is_number('1e3'))  # True

# 测试 Unicode
# 阿拉伯语 5
print(is_number('٥'))  # True
# 泰语 2
print(is_number('๒'))  # True
# 中文数字
print(is_number('四'))  # True
# 版权号
print(is_number('©'))  # False
```
Python 判断奇数偶数
```python
# -*- coding: UTF-8 -*-

# Filename : test.py
# author by : www.runoob.com

# Python 判断奇数偶数
# 如果是偶数除于 2 余数为 0
# 如果余数为 1 则为奇数

num = int(input("输入一个数字: "))
if (num % 2) == 0:
   print("{0} 是偶数".format(num))
else:
   print("{0} 是奇数".format(num))
```
Python 判断闰年
```python
# -*- coding: UTF-8 -*-
 
# Filename : test.py
# author by : www.runoob.com
 
year = int(input("输入一个年份: "))
if (year % 4) == 0:
   if (year % 100) == 0:
       if (year % 400) == 0:
           print("{0} 是闰年".format(year))   # 整百年能被400整除的是闰年
       else:
           print("{0} 不是闰年".format(year))
   else:
       print("{0} 是闰年".format(year))       # 非整百年能被4整除的为闰年
else:
   print("{0} 不是闰年".format(year))
```
Python 获取最大值函数
```python
# -*- coding: UTF-8 -*-

# Filename : test.py
# author by : www.runoob.com

# 最简单的
print(max(1, 2))
print(max('a', 'b'))

# 也可以对列表和元组使用
print(max([1, 2]))
print(max((1, 2)))

# 更多实例
print("80, 100, 1000 最大值为: ", max(80, 100, 1000))
print("-20, 100, 400最大值为: ", max(-20, 100, 400))
print("-80, -20, -10最大值为: ", max(-80, -20, -10))
print("0, 100, -400最大值为:", max(0, 100, -400))
```
Python 质数判断
```python
# -*- coding: UTF-8 -*-

# Filename : test.py
# author by : www.runoob.com

# Python 程序用于检测用户输入的数字是否为质数

# 用户输入数字
num = int(input("请输入一个数字: "))

# 质数大于 1
if num > 1:
    # 查看因子
    for i in range(2, num):
        if (num % i) == 0:
            print(num, "不是质数")
            print(i, "乘于", num // i, "是", num)
            break
    else:
        print(num, "是质数")

# 如果输入的数字小于或等于 1，不是质数
else:
    print(num, "不是质数")
```
Python 输出指定范围内的素数
```python
#!/usr/bin/python3
 
# 输出指定范围内的素数
 
# take input from the user
lower = int(input("输入区间最小值: "))
upper = int(input("输入区间最大值: "))
 
for num in range(lower,upper + 1):
    # 素数大于 1
    if num > 1:
        for i in range(2,num):
            if (num % i) == 0:
                break
        else:
            print(num)
```
Python 阶乘实例
```python
#!/usr/bin/python3
 
# Filename : test.py
# author by : www.runoob.com
 
# 通过用户输入数字计算阶乘
 
# 获取用户输入的数字
num = int(input("请输入一个数字: "))
factorial = 1
 
# 查看数字是负数，0 或 正数
if num < 0:
   print("抱歉，负数没有阶乘")
elif num == 0:
   print("0 的阶乘为 1")
else:
   for i in range(1,num + 1):
       factorial = factorial*i
   print("%d 的阶乘为 %d" %(num,factorial))
```
Python 九九乘法表
```python
# -*- coding: UTF-8 -*-
 
# Filename : test.py
# author by : www.runoob.com
 
# 九九乘法表
for i in range(1, 10):
        for j in range(1, i+1):
            print('{}x{}={}\t'.format(i, j, i*j), end='')
        print()
```
Python 斐波那契数列
```python
# -*- coding: UTF-8 -*-

# Filename : test.py
# author by : www.runoob.com

# Python 斐波那契数列实现

# 获取用户输入数据
nterms = int(input("你需要几项？"))

# 第一和第二项
n1 = 0
n2 = 1
count = 2

# 判断输入的值是否合法
if nterms <= 0:
    print("请输入一个正整数。")
elif nterms == 1:
    print("斐波那契数列：")
    print(n1)
else:
    print("斐波那契数列：")
    print(n1, ",", n2, end=" , ")
    while count < nterms:
        nth = n1 + n2
        print(nth, end=" , ")
        # 更新值
        n1 = n2
        n2 = nth
        count += 1
```
Python 阿姆斯特朗数
```python
# Filename : test.py
# author by : www.runoob.com
 
# Python 检测用户输入的数字是否为阿姆斯特朗数
 
# 获取用户输入的数字
num = int(input("请输入一个数字: "))
 
# 初始化变量 sum
sum = 0
# 指数
n = len(str(num))
 
# 检测
temp = num
while temp > 0:
   digit = temp % 10
   sum += digit ** n
   temp //= 10
 
# 输出结果
if num == sum:
   print(num,"是阿姆斯特朗数")
else:
   print(num,"不是阿姆斯特朗数")
```
Python 十进制转二进制、八进制、十六进制
```python
# -*- coding: UTF-8 -*-

# Filename : test.py
# author by : www.runoob.com

# 获取用户输入十进制数
dec = int(input("输入数字："))

print("十进制数为：", dec)
print("转换为二进制为：", bin(dec))
print("转换为八进制为：", oct(dec))
print("转换为十六进制为：", hex(dec))
```
Python ASCII码与字符相互转换
```python
# Filename : test.py
# author by : www.runoob.com

# 用户输入字符
c = input("请输入一个字符: ")

# 用户输入ASCII码，并将输入的数字转为整型
a = int(input("请输入一个ASCII码: "))


print( c + " 的ASCII 码为", ord(c))
print( a , " 对应的字符为", chr(a))
```
Python 最大公约数算法
```python
# Filename : test.py
# author by : www.runoob.com

# 定义一个函数
def hcf(x, y):
    """该函数返回两个数的最大公约数"""

    # 获取最小值
    if x > y:
        smaller = y
    else:
        smaller = x

    for i in range(1, smaller + 1):
        if ((x % i == 0) and (y % i == 0)):
            hcf = i

    return hcf


# 用户输入两个数字
num1 = int(input("输入第一个数字: "))
num2 = int(input("输入第二个数字: "))

print(num1, "和", num2, "的最大公约数为", hcf(num1, num2))
```
Python 最小公倍数算法
```python
# Filename : test.py
# author by : www.runoob.com

# 定义函数
def lcm(x, y):
    #  获取最大的数
    if x > y:
        greater = x
    else:
        greater = y

    while (True):
        if ((greater % x == 0) and (greater % y == 0)):
            lcm = greater
            break
        greater += 1

    return lcm


# 获取用户输入
num1 = int(input("输入第一个数字: "))
num2 = int(input("输入第二个数字: "))

print(num1, "和", num2, "的最小公倍数为", lcm(num1, num2))
```
Python 简单计算器实现
```python
# Filename : test.py
# author by : www.runoob.com

# 定义函数
def add(x, y):
    """相加"""

    return x + y


def subtract(x, y):
    """相减"""

    return x - y


def multiply(x, y):
    """相乘"""

    return x * y


def divide(x, y):
    """相除"""

    return x / y


# 用户输入
print("选择运算：")
print("1、相加")
print("2、相减")
print("3、相乘")
print("4、相除")

choice = input("输入你的选择(1/2/3/4):")

num1 = int(input("输入第一个数字: "))
num2 = int(input("输入第二个数字: "))

if choice == '1':
    print(num1, "+", num2, "=", add(num1, num2))

elif choice == '2':
    print(num1, "-", num2, "=", subtract(num1, num2))

elif choice == '3':
    print(num1, "*", num2, "=", multiply(num1, num2))

elif choice == '4':
    print(num1, "/", num2, "=", divide(num1, num2))
else:
    print("非法输入")
```
Python 生成日历
```python
# Filename : test.py
# author by : www.runoob.com

# 引入日历模块
import calendar

# 输入指定年月
yy = int(input("输入年份: "))
mm = int(input("输入月份: "))

# 显示日历
print(calendar.month(yy,mm))
```
