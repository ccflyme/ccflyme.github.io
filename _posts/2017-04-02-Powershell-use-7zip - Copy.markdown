---
layout:     post
title:      "powershell中使用7zip压缩文件（转载）"
subtitle:   ""
date:       2017-04-02
author:     "Tesla9527"
header-img: "img/home-bg-art.jpg"
catalog:    false
tags:
    - Powershell
---
原文地址： [http://stackoverflow.com/questions/25287994/running-7-zip-from-within-a-powershell-script](http://stackoverflow.com/questions/25287994/running-7-zip-from-within-a-powershell-script)
```powershell
if (-not (test-path "$env:ProgramFiles\7-Zip\7z.exe")) {throw "$env:ProgramFiles\7-Zip\7z.exe needed"} 
set-alias sz "$env:ProgramFiles\7-Zip\7z.exe"  

$Source = "c:\BackupFrom\backMeUp.txt" 
$Target = "c:\BackupFolder\backup.zip"

sz a -mx=9 $Target $Source
```





