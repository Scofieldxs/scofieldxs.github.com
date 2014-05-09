---
layout: post
title: java 容器
cover: cover_2.jpg
date:   2014-05-09 12:00:00
categories: posts
---
<br/>
<br/>
java:容器类
===

---

+ 容器类库分为两个：Collection 和 Map

##Collection
+ 有三个子接口：
	+ List
	+ Set
	+ Queue

###List
+ ArrayList:基于数组，因此随机访问较好
+ LinkedList：基于链表，因此插入删除较快

###Set
+ 不允许保存重复对象，因此常被用来测试一个对象是否属于一个类
+ HashSet:底层使用散列函数实现，适用快速查找。

---

##Map

+ HashMap:插入和查询开销固定，性能好。
+ LinkedHashMap：链表结构
+ TreeMap：基于红黑树的实现
