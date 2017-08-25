---
layout:     post
title:      "使用Django开发网站"
subtitle:   ""
date:       2017-07-12
author:     "Tesla9527"
header-img: "img/post-bg-alitrip.jpg"
catalog:    true
tags:
    - Django
---

使用工具：
1. PyCharm专业版
2. Python2.7
3. virtualenv
3. mysql
4. HeidiSQL

数据库配置：
```python
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.mysql',
        'NAME': 'database_name',
        'USER': 'root',
        'PASSWORD': 'root',
        'HOST': '127.0.0.1'
    }
}
```
