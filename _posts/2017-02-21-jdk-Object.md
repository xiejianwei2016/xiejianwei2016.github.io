---
date: 2017-02-21 00:00
layout: post
title: java.lang.Object 源代码阅读
categories: jdk1.7
---

java.lang.Object类作为类继承层次中的根。Obejct是所有类的父类。所对有象，包括数组，
都实现了Object 类中的方法。

### 1. Object 类的 toString() 方法
```java
	public String toString() {
		return getClass().getName() + "@" + Integer.toHexString(hashCode());
	}
```
### 例子：
```java
	@Test
	public void toStringTest() {
		Object object = new Object();
		System.out.println(object.toString());
	}
```
运行结果：java.lang.Object@3654919e

解析：返回对象的一个字符串表示：类的全名+“@”+16进制哈希码

### 2. Object 类的 equals() 方法
```java
	public boolean equals(Object obj) {
		return (this == obj);
	}
```
### 例子：
```java
	@Test
	public void equalsTest() {
		Object object = new Object();
		Object object2 = new Object();
		System.out.println(object.equals(object2));
	}
```
运行结果：false

解析：判断调用 equals() 方法的引用与传递进来参数的引用是否一致，即这两个引用是否指向同一个对象。它等价于 == 。

Object 类的 equals 方法特点：  
a)自反性：x.equals(x) 应该返回 true。  
b)对称性：x.equals(y) 为 true，那么 y.equals(x) 也为 true。  
c)传递性：x.equals(y) 为 true，并且 y.equals(z) 为 true，那么 x.equals(z) 也应该为 true。  
d)一致性：x.equals(y) 第一次调用为 true，那么 x.equals(y) 的第二次、第三次、第n次调用，  也应该为 true，前提是在比较之间没有修改 x 和 y。  
e)对于非空引用那个 x，x.equals(null) 返回 false。