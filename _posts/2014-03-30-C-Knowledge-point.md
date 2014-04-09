---
layout: post
title: C Knowledge-point
cover: 1166365595121c5dc7l.jpg
date:   2013-12-09 12:00:00
categories: posts
---
<br/>
<br/>

C Knowledge:point
===
<br/>
<br/>
###1.字符串常量
+ 它的值是个指针常量
			
		"xyz"+1
>表示指向"xyz"的指针值加1，即指向y

>用处：

		void mystery(int n)
		{			
			printf("%s\n","**********"+10-n);
		}
>打印n个“*”，n在0-10之间


<br/>
<br/>
<br/>
###2.指针传递
>问题描述：想获得一个数组长度，得到的答案是：

	sizeof(s) / sizeof(int)
>实验发现不行，原因是：当数组作为函数的参数进行传递时，该数组自动退化为同类型的指针。
>
>所以当把数组传到函数里调用这个方法结果为1.

