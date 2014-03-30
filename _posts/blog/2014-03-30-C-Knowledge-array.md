---
layout: post
title: C Knowledge array
category: blog
---
C Knowledge:数组
===
<br/>

>* int b[4]

   >&#8194;&#8194;&#8194; b的类型就是
>*"指向int的常量指针"*

>* 与指针变量的区别是：不能修改常量值

>* 编译器不检查下标（是否合法，是否越界）。因为代价太大了。

>* 效率上，下标<=指针

>* 二维数组传参：
	
	void func(int mat[][10])
	void func(int(*mat)[10])
>***mat是不对的，因为它表示指向指针的指针，而 int(*mat)[10]表示一个指向有10个元素的数组的指针


![](http://img3.douban.com/view/photo/raw/public/p2164194854.jpg)