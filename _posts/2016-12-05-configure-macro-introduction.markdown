---
layout: post
title:  "configure.ac 和Makefile.am中常用的宏的介绍"
date:   2016-12-05 19:24:24 +0800
categories: automake, autoconf, makefile
---
# configure.ac 中的一些配置     

AC_PREREQ(2.5.9)                        #工具版本号，不需要关系      
AC_INIT(atlas, 1.0, tsthght@163.com)    #指示：可执行名称+版本号+BUG-REPORT     
AC_CONFIG_SRCDIR([src/main.c])          #检验源文件是否缺失     

AM_CONFIG_HEADER(config.h)              #     
AM_INIT_AUTOMAKE(atlas, 1.0, tsthght@163.com) #可选     

#checks for programs     
AC_PROG_CC                              #检查cc，如果c++则AC_PROG_CXX    

#checks for libraies    
AC_CHECK_LIB([lib], [func], [if_exist_action], [not_exist_action]) #检查库, 例如：AC_CHECK_LIB([m], [sqrt])     

AC_PROG_RANLIB                         #使用静态库时，需要     
AC_PROG_LIBTOOL                        #使用动态库时，需要    

#checks for header files    
AC_CHECK_HEADERS([float.h malloc.h stdlib.h])     

#checks for typedefs, structures, and compiler characteristics     
#AC_C_CONST    

#checks for libray functions      
#AC_FUNC_MALLOC     
AC_CHECK_FUNCS([pow sqrt])     

#输出的文件，有几个Makefile.am就有几个Makefile     
AC_OUTPUT([     
	Makefile    
	src/Makefile     
	lib/Makefile     
])     

# Makefile.am中的一些配置     

AUTOMAKE_OPTIONS=foreign     
SUBDIRS=lib src                          #指示所有的子Makefile.am所在的目录     
CURRENTPATH=$(shell /bin/pwd)            #指示当前路径     
INCLUDES=-l$(CURRENTPATH)/include        #指示src中头文件之外的其他头文件的目录，需要EXPORT到子Makefile.am中去     
export INCLUDES    
#生成lib需要的一些配置
noinst_LIBRARIES=libnew.a                #noinst:not install      
libnew_a_SOURCES=new.c                   #注意.换成_     
#成成可执行文件需要的一些配置     
bin_PROGRAMS=main        
main_SOURCES=main.h main.c              
main_LDADD=$(top_srcdir)/lib/libnew.a      

# 参考    
[1] [Makefile实际用例分析](http://blog.csdn.net/shanshanpt/article/details/17200035)    

