---
layout: post
title: C Knowledge 
category: blog
---

C Knowledge
===

<br/>
###1.最大堆最小堆
>堆的用处在于最快的找到最大值，最小值
>
>取走最大值并重新构造的时间复杂度为O(logn)，其他方法为O(n)。
>
>主要用在调度算法中，比如优先级调度

<br/>


<br/>
###2.register
>register用于请求编译器_尽可能_将变量存于CPU内部寄存器中，而不是通过内存寻址访问，而提高效率

	register int *p1,*p2;
	for(p1=x,p2=y;p1<&x[SIZE];)
	{
		*p1++=*p2++
	}
>这样执行操作会快的多

###3.各种数据类型长度
+ size of int is:   4
+ size of char is:   1
+ size of short int is:   2
+ size of double is:   8
+ size of unsigned int is:   4
+ size of float is:   4
+ size of long double is:   8
+ size of long int is:   4
+ size of long int is:   4
+ size of unsigned char is:   1
+ size of signed char is:   1
+ size of unsigned long int is:   4
+ size of signed int is:   4
+ size of unsigned short int is:   2
+ size of signed short int is:   2
+ size of signed int is:   4
+ size of signed long int is:   4


###4.宏的优势
> 可以完成一些在不需要数据类型情况下的操作
	
	
	#define MALLOC(n,type)\
	((type *)malloc((n)*sizeof(type)))
	
	#define MAX(a,b) ((a)>(b) ? (a) : (b))

>MAX可以对任何数据类型进行比较

>宏的执行速度比函数快，因为省了调用与返回的开销

###小知识
+ int能表示的最大，最小的数：

		static const int MAX=(int)((unsigned)~0>>1);
		static const int MIN=-(int)((unsigned)~0>>1)-1;

![](http://fa.topit.me/a/be/0a/11303328811bc0abeal.jpg)