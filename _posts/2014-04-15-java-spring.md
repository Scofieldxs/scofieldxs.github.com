---
layout: post
title: java spring
date:   2014-04-15 12:00:00
categories: posts
---
java:spring
===
+ 三个核心组件
	+ core
	+ context(为spring提供运行时环境)
	+ beans(最重要，spring为面向bean编程)


<br/>

+ spring解决的最关键问题：
 	+ 把对象间的依赖关系用配置文件管理（依赖注入）
 	+ 用IoC容器管理，spring通过把对象包裹在bean里实现对象管理

<br/>

+ spring响应流程

![image](../images/20130921205445062.jpg)
 	

##IoC
把传统上由程序代码直接操控的对象调用权交给容器，通过容器实现对象的装配和管理

##AOP
+ spring对bean对象的AOP处理有两种方式：
	+ 有接口的类：JDKDynamicAopProxy
	+ 普通类：CglibProxyFactory


##Servlet
+ servlet是对http协议做面向对象的封装
	+ HttpServletRequest :对应http请求，通过它可以获取请求相关	信息，如url,cookie,请求参数
	+ HttpServletResponse：对应http回应


##session
+ 针对http无连接状态，session用来保存用户连接状态信息
+ 本质为服务器端的哈希表



