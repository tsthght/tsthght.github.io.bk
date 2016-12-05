---
layout: post
title:  "automake autoconf 入门教程"
date:   2016-12-03 22:00:24 +0800
categories: automake, autoconf, makefile
---
# Makefile介绍    
1. Makefile让编译器知道编译一个文件所需依赖的其他的文件，当这些依赖文件有变化时，编译器会自动的发现最终的生成文件已经过时，而仅仅重新编译过时的模块    
2. 自己写的Makefile不一定符合惯例，且会和开发环境重度耦合，automake解决了手工书写Makefile的诸多问题   
3. 使用automake时，程序开发人员只需要写一些简单的含有预定义的宏文件   

# 环境配置   
1. yum install automake    
2. yum install autoconf   

# 举例hellworld    

1. 创建一个示例程序: helloworld    
> mkdir hellowrld    
> cd helloworld    

```
#include <stdio.h>
int main(int argc, char **argv) {     
    printf("%s", "hello, linux world!\n");     
    return 0;
}    
```

2. 生成config   
> autoscan    
> mv configure.scan configure.ac    

    修改configure.ac中的内容:
```   
AC_INIT(helloworld.c)
AM_INIT_AUTOMAKE(helloworld, 1.0)    
AC_PROG_CC    
AC_OUTPUT(Makefile)   
```
> aclocal    
> autoconf   

    通过上述命令，分别阐述了:aclocal.m4和configure

3. 新建Makefile.am   
> touch Makefile.am   

    内容如下：   
```     
AUTOMAKE_OPTIONS=foreign    
bin_PROGRAMS=hellowrld   
helloworld_SOURCES=helloworld.c   
```

4. 运行automake    
> automake --add-missing    

5. 执行configure生成Makefile   
> ./configure   

# 生成的Makefile中预定义操作    
> make    
> make clean    
> make install   
> make dist   
> make distcheck   




# 参考   
[1] [automake,autoconf使用详解](http://www.laruence.com/2009/11/18/1154.html)   

