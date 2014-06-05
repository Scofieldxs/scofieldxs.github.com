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
+ Vector非常类似ArrayList，但是Vector是同步的。使用了synchronized方法（线程安全），通常性能上较ArrayList差
	+ Stack继承自Vector，当做堆栈使用。
###Set
+ 不允许保存重复对象，因此常被用来测试一个对象是否属于一个类
+ HashSet:底层使用散列函数实现，适用快速查找。

---

##Map

+ HashMap:插入和查询开销固定，性能好。
+ LinkedHashMap：链表结构
+ TreeMap：基于红黑树的实现

###Collection vs Collections
+ Collection是集合类的一个顶级接口
+ Collections是一个工具类，提供一系列的静态方法，用于排序，搜索，不能实例化。

			List list=new ArrayList();
			Collections.sort(list);

###HashMap vs HashTable
+ HashMap是Hashtable轻量级实现，非线程安全，允许空，
+ Hashtable方法是Synchronize的。
