---
layout: post
title: java.util.LinkedList 源代码阅读
date: 2017-03-03 15:35
categories: jdk1.7
---

* content
{:toc}
## 前言
（1）LinkedList的内部实现是双向链表，继承了AbstractSequentialList，实现了List, Deque, Cloneable, Java.io.Serializable接口，因此LinkdeList本身支持就支持双端队列操作。LinkedList**允许所有元素（包括 null）**。除了实现 List 接口外，LinkedList 类还为在列表的开头及结尾 get、remove 和 insert 元素提供了统一的命名方法。这些操作允许将链接列表用作堆栈、队列或双端队列。
