---
layout: post
title: C Knowledge-array
cover: 1166365595121c5dc7l.jpg
date:   2013-12-09 12:00:00
categories: posts
---
<br/>
<br/>
C Knowledge:array
===
<br/>
<br/>

			int b[4]

+ b的类型就是*"指向int的常量指针"*

* 与指针变量的区别是：不能修改常量值

* 编译器不检查下标（是否合法，是否越界）。因为代价太大了。

* 效率上，下标<=指针

* 二维数组传参：
	
	void func(int mat[][10])
	void func(int(*mat)[10])
>***mat是不对的，因为它表示指向指针的指针，而 int(*mat)[10]表示一个指向有10个元素的数组的指针


![](http://f2.topit.me/2/3f/31/11467153000ca313f2o.jpg)