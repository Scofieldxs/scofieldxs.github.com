---
layout: post
title: java常用操作
cover: cover_5.jpg
date:   2014-05-12 12:00:00
categories: posts
---
<br/>
<br/>


###String 
+ str.charAt(i)：拿某个位置的值
+ char[] ch=str.toCharArray()：string转字符数组
+ String str=new String(ch)：数组转字符串


###other
+ char转int

		char a='1';
		int i=Integer.parseInt(String.valueOf(a));

+ int转String

		int as=1;
		String string=String.valueOf(as);
