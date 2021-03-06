---
date: 2017-10-03 22:46
layout: post
title: java8 lambda表达式
categories: java8
---

* content
{:toc}

### 何为 lambda 表达式
----------------------------------------
Java Lambda表达式是一种匿名函数；它是没有声明的方法，即没有访问修饰符、返回值声明和名字。

### 为何需要 lambda 表达式
----------------------------------------
在Java中，我们无法将函数作为参数传递给一个方法，也无法声明返回一个函数的方法。

### lambda 表达式作用
----------------------------------------
Lambda 表达式为 Java 添加了缺失的函数式编程特性，使我们能将函数当作一等公民对待。

在将函数作为一等公民的编程语言中，Lambda表达式的类型是函数。<font color="#FF0000">但在Java8中，Lambda表达式是对象，而不是函数，它们必须依附于一类特别的对象类型——函数式接口</font>。

简单的说，<font color="#FF0000">在Java8中，Lambda表达式就是一个函数式接口的实例</font>。这就是Lambda表达式和函数式接口的关系。也就是说，只要一个对象是函数式接口的实例，那么该对象就可以用Lambda表达式来表示。所以以前用匿名内部类表示的现在都可以用Lambda表达式来写。