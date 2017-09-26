---
date: 2017-05-28 10:14
layout: post
title: java8 函数式接口
categories: java8
---

### 1.什么是函数式接口呢？
----------------------------------------

函数式接口是Java8新增加的内容。如果一个接口<font color="#FF0000">只有一个抽象方法</font>，那么该接口就是函数式接口。


### 2.FunctionalInterface 注解
----------------------------------------
java.lang.FunctionalInterface（该注解位于java.lang包下）

让我们看看 javadoc 是怎么描述的？

```java
@Documented
@Retention(RetentionPolicy.RUNTIME)
@Target(ElementType.TYPE)
public @interface FunctionalInterface {}
```

@FunctionalInterface是一种信息化的注解类型，表示声明的接口是一个函数式接口(该接口由Java语言规范定义)。
在概念上，函数式接口只有一个抽象方法。由于默认方法有一个实现，所以它们不是抽象的。**如果一个接口声明了一个抽象方法，该抽象方法覆盖了 java.lang.Object 的 public 方法，那么不会计入接口抽象方法的个数。
因为任何接口的实现类都将直接或间接地继承自java.lang.Object。**

请注意，可以使用<font color="#FF0000">lambda表达式，方法引用或构造方法引用创建函数接口的实例</font>。

使用此注解注释类型，编译器如果不满足下面两条就会生成错误消息：
*   被注释的类型是接口类型，不是注解，枚举，类。

*   被注释的类型必须满足函数式接口的要求。

然而，无论接口声明中是否存在FunctionalInterface注解，编译器都会将符合函数式接口定义的任何接口视为函数式接口。

总结：
*   <font color="#FF0000">如果我们在某个接口上声明了FunctionalInterface注解，那么编译器会按照函数式接口的定义来要求该接口。</font>


*   <font color="#FF0000">如果某个接口只有一个抽象方法，但我们并没有给该接口声明FunctionalInterface注解，那么编译器依旧会将该接口看做是函数式接口。</font>