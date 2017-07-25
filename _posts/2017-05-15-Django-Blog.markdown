---
layout:     post
title:      "使用Django搭建个人博客"
subtitle:   ""
date:       2017-05-15
author:     "Tesla9527"
header-img: "img/home-bg-art.jpg"
catalog:    true
tags:
    - Python
    - Django
---
参考资料：
[https://www.pythonprogramming.net/django-web-development-with-python-intro/](https://www.pythonprogramming.net/django-web-development-with-python-intro/)

完成后的代码地址：
[https://github.com/Tesla9527/django_tutorial](https://github.com/Tesla9527/django_tutorial)

下面对细节进行分析：

## First Website
这篇讲解了如果在project里面通过manage.py新建app，在views.py文件中定义方法，在新建的app中配置url.py以及project的url.py，在settings.py中include新建的app。

webapp/views.py
```python
from django.shortcuts import render
from django.http import HttpResponse

def index(request):
    return HttpResponse("<h2>HEY!</h2>")
```

webapp/urls.py
```python
from django.conf.urls import url
from . import views

urlpatterns = [
    url(r'^$', views.index, name='index'),
]
```

mysite/urls.py
```python
from django.conf.urls import url,include
from django.contrib import admin

urlpatterns = [
    url(r'^admin/', admin.site.urls),
    url(r'^webapp/', include('webapp.urls')),
]
```

mysite/settings.py
```python
# ...this is just a slice of code within settings.py 
# do not delete the other code
# just add 'webapp' to the list.
INSTALLED_APPS = [
    'webapp',
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',
]
```

## Jinja Templates

## Design with HTML/CSS

## Jinja Variables

## Beginning a Blog

## Views and Templates

## Database migrations

## Admin control panel

## Finishing blog

## Publishing

## Securing Django