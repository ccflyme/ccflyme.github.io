---
layout:     post
title:      "Use dotTrace to analysis web application performance"
subtitle:   ""
date:       2016-08-14
author:     "Tesla9527"
header-img: "img/home-bg-art.jpg"
catalog:    false
tags:
    - dotTrace
---

**下面是自己录制的操作视频**

<iframe width="560" height="315" src="https://www.youtube.com/embed/RIdWZCaEjXY" frameborder="0" allowfullscreen></iframe>

---

接下来我会一步一步分析操作方法

1. Open and build the project in visual studio
为了让dotTrace检测到我们的project，我们需要在Visual Studio中打开并编译project。

2. Open dotTrace, select IIS Express in Profile Application

3. Select site in configuration file, Line-by-line in Profiler Options and hit run

4. Open site in IIS Express

5. Get the snapshot and analysis
获取到某段时间的snapshot后，我们就可以清楚地看到各个方法所花的时间，然后针对这些方法进行更一步的分析。
