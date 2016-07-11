---
layout:     post
title:      "数据库每日自动备份"
subtitle:   ""
date:       2016-07-12
author:     "Tesla9527"
header-img: "img/home-bg-o.jpg"
catalog:    true
tags:
    - 工作
---
```sql
DECLARE @SQLStatement VARCHAR(2000)
SET @SQLStatement = 'S:\DbTemp\Dfyf.Bpm.bak'
BACKUP DATABASE [Dfyf.Bpm] TO  DISK = @SQLStatement;
```

```powershell
Add-Type -Assembly "System.IO.Compression.FileSystem" ;
[System.IO.Compression.ZipFile]::CreateFromDirectory("S:\DbTemp\", "S:\DbBackUp\Dfyf.Bpm.bak.zip");
$fileName = 'S:\DbBackUp\Dfyf.Bpm.bak.zip'
$fileObj = get-item $fileName
# Get the date
$DateStamp = get-date -uformat "%Y-%m-%d@%H-%M-%S"
$extOnly = $fileObj.extension

if ($extOnly.length -eq 0) {
   $nameOnly = $fileObj.Name
   rename-item "$fileObj" "$nameOnly-$DateStamp"
   }
else {
   $nameOnly = $fileObj.Name.Replace( $fileObj.Extension,'')
   rename-item "$fileName" "$nameOnly-$DateStamp$extOnly"
   }
Remove-Item S:\DbTemp\Dfyf.Bpm.bak
```
