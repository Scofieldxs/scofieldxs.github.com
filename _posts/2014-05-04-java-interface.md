---
layout: post
title: java 接口
cover: cover_1.jpg
date:   2014-05-04 12:00:00
categories: posts
---
<br/>
<br/>

java 接口
===
使用接口的原因：

+ 能够向上转型为多个基类型

		intervface CanFight{
			void fight();
		}

		interface CanSwin{
			void swim();
		}

		class hero implements CanFight,CanSwim{
			public void swim(){}
			public void fight(){}
		}

		public class Adventure{
			public static void t(CanFight x){x.fight();}
			public static void u(CanSwim x){x.swim();}

			public static void main(String[] args){
				Hero h=new Hero();
				t(h);//向上转型
				u(h);//向上转型

---
##接口中的域
+ 接口中的域都自动是tatic和final的
