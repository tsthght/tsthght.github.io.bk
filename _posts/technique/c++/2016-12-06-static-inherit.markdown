---
layout: post
title: 类中static变量的继承
date: 2016-12-06 23:05:31 +0800
category: 技术
tags:     cplusplus static
keywords: static c++
description: 
---
* c++中静态变量**不能被继承**       
验证代码：       

```     
#include <iostream>
using namespace std;
class A {
public:
        static int num;
};
int A::num = 100;
class B:public A {
public:
        int i;
        B(int m):i(m) {}
};

int main(int argc, char **argv) {
        A *a = new B(5);
        cout<<a->num <<endl;
        a->num = 100;
        cout<<a->num <<endl;

        cout<<B::num <<endl;
        cout<<A::num <<endl;

        cout<< &B::num <<endl;
        cout<< &A::num <<endl;
        cout<< &a->num <<endl;

        B::num = 150;
        cout<<A::num <<endl;

        return 0;
}

output:
10
100
100
100
0x10fa15088
0x10fa15088
0x10fa15088
150
```     
参考     
[1] [c++中静态变量](http://bbs.bccn.net/thread-340099-1-1.html)     

