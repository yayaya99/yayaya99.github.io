---
title: java中局部变量的初始化问题
categories: Java
tags:
  - Java
  - 局部变量
abbrlink: 62525
date: 2019-08-02 16:16:21
---
java中局部变量的初始化问题
<!--more--> 
## Java中局部变量必须初始化但成员变量不必须初始化

其实无论成员变量还是局部变量都要初始化，只是JVM帮我们初始化了成员变量。

JVM在初始化对象时就可以初始化成员变量。

在类的加载中，我们定义的成员变量进行了两次初始化，一次赋默认初值（0值，boolean赋为false），一次赋自定义的初值。
而对于方法中的局部变量，需要进栈执行，这个过程是没有赋初值过程的。

还有种情况为：定义的局部变量没有赋值，也没有报错，是因为局部变量没有被调用


