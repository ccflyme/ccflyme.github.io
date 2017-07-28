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

>Jinja is a Python templating engine, aimed at helping you to do dynamic things with your HTML like passing variables, running simple logic, and more! With Jinja, this denotes logic. 

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

这篇新建了一个contact的方法，用来render contact page的内容。其中content的内容通过变量的方式传入。关于url的配置，文中讲到了需要将settings.py中include的personal.urls前面的r'^$'改为r'^'，因为r'^$'说明通过url到personal app不允许有任何text。看到这里，突然有了一种和我做UI自动化测试一种类似的设计，就是page object的概念。做自动化测试时，是以page为对象，来存储ui元素，已经页面上的操作方法。这里开发网站的时候，貌似也是以page的概念。通过url路由到对应的view里面的方法，然后这个方法又将内容render出来。不论这个内容是静态的，还是通过各种model读取展示出来的。

## Beginning a Blog

>We're going to cover working with models in Django

- python manage.py startapp blog 新建一个app "blog"
- 在settings.py中install blog app
	
	INSTALLED_APPS = [
    'personal',
    'blog',
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',
]

- 配置blog app的url
```python
from django.conf.urls import url, include
from django.contrib import admin

urlpatterns = [
    url(r'^admin/', admin.site.urls),
    url(r'^', include('personal.urls')),
    url(r'^blog/', include('blog.urls')),
]
```

- 新建blog的model class
```python
from django.db import models

class Post(models.Model):
    title = models.CharField(max_length = 140)
    body = models.TextField()
    date = models.DateTimeField()

    def __str__(self):
        return self.title
```

## Views and Templates

>we're going to employ some further Django magic and skip that part entirely with some generic views.
blog/urls.py
```python
from django.conf.urls import url, include
from django.views.generic import ListView, DetailView
from blog.models import Post

urlpatterns = [ 
                url(r'^$', ListView.as_view(
                                    queryset=Post.objects.all().order_by("-date")[:25],
                                    template_name="blog/blog.html")),
            ]
```

blog/templates/blog/blog.html
```python
{% extends "personal/header.html" %}
{% block content %}
	{% for post in object_list %}
		<h5>{{ post.date|date:"Y-m-d" }}<a href="/blog/{{post.id}}">  {{ post.title }}</a></h5>
	{% endfor %}
{% endblock %}
```

## Database migrations

## Admin control panel

## Finishing blog

## Publishing

## Securing Django