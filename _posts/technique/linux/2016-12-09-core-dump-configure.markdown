---
layout: post
title:  core文件的设置
date:   2016-12-09 14:42:18 +0800
category: 技术
tags:   coredump
keywords: linux coredump
description: 
---
1. core文件的生成开关和文件大小限制     
```
ulimit -a
ulimit -c filesize
```

2. core文件的名称和生成路径    

```
1. /proc/sys/kernel/core_uses_pid可以控制core文件的文件名中是否添加pid作为扩展。文件内容为1，表示添加pid作为扩展名，生成的core文件格式为core.xxxx；为0则表示生成的core文件同一命名为core。
echo "1" > /proc/sys/kernel/core_uses_pid

2. proc/sys/kernel/core_pattern可以控制core文件保存位置和文件名格式。
echo "/corefile/core-%e-%p-%t" > core_pattern
```

