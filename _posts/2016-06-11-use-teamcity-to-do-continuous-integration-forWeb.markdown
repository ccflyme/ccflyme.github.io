---
layout:     post
title:      "使用TeamCity做Web app的持续编译、发布和部署"
subtitle:   ""
date:       2016-06-11
author:     "Tesla9527"
header-img: "img/post-bg-unix-linux.jpg"
catalog:    true
tags:
    - TeamCity
---


## 新建Configuration用来编译工程和打包发布出来的文件

- 新建Build Step-编译工程

  这一步会将source code拿到TeamCity的一个work directory，并完成编译。

- 新建Build Step-发布站点程序文件

	Build file path中填写的文件是publish app时使用的配置文件，我用的是[David Wilson](https://essenceofcode.com/about/)的[文件](https://essenceofcode.com/2012/08/20/using-msbuild-and-team-city-for-deployments-part-2-continuous-integration-build-and-verify/),
	代码片段如下：

```xml
<?xml version="1.0" encoding="utf-8"?>
<Project DefaultTargets="Transform"
xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
<Target Name="Publish">
  <Message Text="Configuration: $(Configuration)" />
  <!-- Platform=Any Cpu for Solution Files, Platform=AnyCpu for project files-->
  <MSBuild Projects="$(Projects)" Properties="Platform=AnyCPU;
                                              Configuration=$(Configuration);
                                              AutoParameterizationWebConfigConnectionStrings=False;
                                              DeployOnBuild=True;
                                              DeployTarget=Package;
                                              PackageLocation=_package;
                                              PackageAsSingleFile=False;"/>
</Target>
</Project>
```

-	这一步完成后会在obj/Release/Package/PackageTmp 中生成publish完了之后的文件，这个时候我们将IIS的站点的物理地址指向这里，就完全可以运行起来了。但我们还需要对web.config文件做一些修改，所以暂时我们将生成的相关文件打包好，在下一个configuration中再去修改和部署。
