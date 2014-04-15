---
layout: post
title: java 继承
date:   2014-04-15 12:00:00
categories: posts
---
Java 继承
===
+ _extends_
+ 所有类都是隐式的从Java标准根类Object进行继承

###设计思路：
+ 父类的数据成员设置为private，方法设置为public

###复用类的三种方式：
+ 组合（在一个类里生成另一个类的实例）
+ 继承
+ 代理（between 组合 and 继承）·

		public class SpaceControl{
			void up(int velocity){}
		}//基类

		public class space{
			private SpaceControl control=new SpaceControl();
			public void up(int velocity){
				control.up(velocity);
			}
		}

###组合与继承的选择
+ 组合是“has-a”关系
+ 继承是“is-a”关系

###protected
+ 就用户而言是private，就继承此类的子类是public

###向上转型
+ 子类当基类用

###final
+ 数据
	+ 不改变的编译时常量
		+ static强调只有一份
	+ 指向一个对象，无法指向另一个

+ 方法
	+ 防止继承类修改该方法
+ 类
	+ 不能继承该类 