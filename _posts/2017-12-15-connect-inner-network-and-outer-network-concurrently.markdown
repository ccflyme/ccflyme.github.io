---
layout:     post
title:      "同时连接内网和外网"
subtitle:   ""
date:       2017-12-05
author:     "Tesla9527"
header-img: "img/post-bg-alitrip.jpg"
catalog:    false
tags:
    - route
---

删除默认路由：route delete 0.0.0.0

配置外网路由：route add 0.0.0.0 mask 0.0.0.0 192.168.8.1 -p metric 1

配置内网路由：route add 20.0.25.0 mask 255.255.255.0 20.41.47.1 -p metric 30

备注：
192.168.8.1为外网网关（配置时用实际外网网关）
20.0.25.0为内网ip网段，255.255.255.0为外网子网掩码（配置时用实际外网ip网段和子网掩码）
metric后面的值代表跃点数
