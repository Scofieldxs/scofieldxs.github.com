---
layout: post
title: C Knowledge-string
cover: 1166365595121c5dc7l.jpg
date:   2013-12-09 12:00:00
categories: posts
---
<br/>
<br/>


C Knowledge:string
===
<br/>
<br/>
+ strlen()返回的是无符号,所以：

		if(strlen(x)>=strlen(y))  //是对的
		if(strlen(x)-strlen(y)>=0)  //结果永远为正

<br/>

+ strcpy需要保证目标数组足够大，否则会覆盖数组后面的内存
	
		char message[]="Original message"
		strcpy(message,"A different message")


+ strtok

	+ 定义：作用于字符串s，以包含在delim中的字符为分界符，将s切分成一个个子串；
   如果，s为空值NULL，则函数保存的指针SAVE_PTR在下一次调用中将作为起始位置。
	+ 对原作用域做了修改，在找到的第一个位置修改成'\0'
	+ 以某个分隔符分割字符串，标准写法：
	
			static char whitespace[]=" \t\f\r\v\n";
			char *token;
			token=strtok(line,whitespace);
			for(;token!=NULL;token=strtok(NULL,whitespace))
			{
				printf("Next is %s\n",token);
			}
	
 

+ 去掉重复字符串
	strcpy(dup,dup+1)//dup为重复字符出现位置


<br/>
![](http://i9.topit.me/9/e8/9e/1153911952edc9ee89l.jpg)