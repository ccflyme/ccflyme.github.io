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

>这篇讲解了如何在project里面通过manage.py新建app，在views.py文件中定义方法，在新建的app中配置url.py以及project的url.py，在settings.py中include新建的app。

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

>Jinja is a Python templating engine, aimed at helping you to do dynamic things with your HTML like passing variables, running simple logic, and more! With Jinja, you will notice we are using {% %}, this denotes logic. For variables, you will see {%{% }}.

Jinja模板的使用，可以查阅相关文档。和上一篇相比，view.py中的内容修改了。之前是直接返回HttpResponse内容，现在通过render html的方式。html内容的组成就通过Jinja引擎来做了。
```python
from django.shortcuts import render

def index(request):
    return render(request, 'personal/home.html')
```

## Design with HTML/CSS

>We're going to use Bootstrap, which is a popular HTML/CSS and some javascript package that greatly helps people who are design deficient. Bootstrap isn't going to fix you entirely, but it can at least lend a helping hand. 

这篇介绍了使用Bootstrap，让我们页面的样式更好看一点。和上一篇一样，重要的是理解css文件是如何被引用到的。

## Jinja Variables

>In this tutorial, we're going to cover passing variables from Python to our HTML templates.

## Beginning a Blog

## Views and Templates

## Database migrations

## Admin control panel

## Finishing blog

## Publishing

## Securing Django