---
layout: post
title: java基础知识2
cover: cover_5.jpg
date:   2014-06-12 12:00:00
categories: posts
---
<br/>
<br/>
##java基础2

####1.java安全性
1. 编译时错误检查
2. 类装载时检查
3. 字节码校验
4. 沙箱机制，限定访问权限

####2.环境配置
1. path（%JAVA_HOME%\bin\java）：在任何路径下可以使用java命令行
2. JAVA_HOME（C:\jdk1.6）：JDK路径，嫌名字太长用个短的代替
3. classpath(%JAVA_HOME%\lib \dt.jar;%JAVA_HOME%\lib\toos.jar)：为了让程序能找到相应的.class文件。

####权限控制
+ private：同一个类中
+ default：同一个包中
+ protected：子类，同一个包
+ public：任何场合

####xml解析方法
+ DOM解析：解析文件时将整个文档装入内存，适合对xml随机访问，占用内存，文件大时效率低。
+ SAX解析：顺序读取xml文件，适合顺序访问。

####java回调函数
A类调用B类的c方法，然后B类反过来调用A类的d方法。

	public class A implements CallBack {//
		private B b;
	
		public void askQuestion(){
			b.executeMessage(A.this);
		}
	
		public void solve(){}
	}
	
	public class B {
	
		public void executeMessage(CallBack callBack){
			callBack.solve();
		}
	}	

####String StringBuilder StringBuffer
+ String不可变的，当改变String时会生成一个新的String
+ StringBuffer会对对象本身操作，一般比String快。是线程安全的，可用于多线程。
+ Stringbuilder非线程安全，比StringBuffer快，适合单线程。