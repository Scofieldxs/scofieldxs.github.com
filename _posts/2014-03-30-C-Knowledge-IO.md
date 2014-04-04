---
layout: post
title: C Knowledge-IO
cover: 1166365595121c5dc7l.jpg
date:   2013-12-09 12:00:00
categories: posts
---

C Knowledge: I/O
===
###1.输入输出函数
>标准输入输出在ANSI C 库中，头文件：stdio.h，包含了I/O库所需要的声明
>
>流分为两种：文本流（text）和二进制流
>
>FILE包含于stdio.h,是一个用于访问流的数据结构

>对于ANSI C程序，运行时系统必须提供三个流：标准输入，标准输出，标准错误，三个都是指向FILE的指针

###2.perror提供向用户报告错误的简单方法

		FILE *input
		input=fopen("data","r");
		if(input==NULL)
		{
			perror("data");
			exit(0);
		}
>输出：data:No such file or directory