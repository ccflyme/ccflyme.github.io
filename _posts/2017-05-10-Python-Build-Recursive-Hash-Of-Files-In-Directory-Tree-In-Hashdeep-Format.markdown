---
layout:     post
title:      "使用Python的hashdeep检测目录中所有文件的hash值"
subtitle:   ""
date:       2017-05-10
author:     "Tesla9527"
header-img: "img/home-bg-art.jpg"
catalog:    false
tags:
    - Python
---
使用的是[https://gist.github.com/techtonik/5175896](https://gist.github.com/techtonik/5175896),下面我只是增加了一下检测目录和输出文件

```python
import os
import os.path as osp
import hashlib


def filehash(filepath):
    blocksize = 64 * 1024
    sha = hashlib.sha256()
    with open(filepath, 'rb') as fp:
        while True:
            data = fp.read(blocksize)
            if not data:
                break
            sha.update(data)
    return sha.hexdigest()


def get_recursive_hash(dir_root, file_path):
    print('size,sha256,filename')
    hash_output_file = open(file_path, 'w')
    for root, dirs, files in os.walk(dir_root):
        for fpath in [osp.join(root, f) for f in files]:
            size = osp.getsize(fpath)
            sha = filehash(fpath)
            name = osp.relpath(fpath, dir_root)
            print('%s,%s,%s' % (size, sha, name))
            hash_output_file.write('%s,%s,%s\n' % (size, sha, name))
    hash_output_file.close()


get_recursive_hash('E:/Github', 'E:/hash_output_file.txt')
```


