---
layout:     post
title:      "断网环境安装python模块"
subtitle:   ""
date:       2018-01-18
author:     "Tesla9527"
header-img: "img/post-bg-alitrip.jpg"
catalog:    false
tags:
    - Python
---
python的安装还是在联网的情况下通过pip最方便，但有些场景我们没有外网，自己尝试了多种方法，都很麻烦。最后采用如下方式解决：在一台联网的机器上安装好需要的模块，然后将Lib目录打包拷贝到没有外网的机器上的Lib目录下，就ok了。