---
layout: post
title: java 闲杂知识
cover: cover_1.jpg
date:   2014-05-04 12:00:00
categories: posts
---
<br/>
<br/>

java:闲杂知识
===
---

##序列化
+ 就是讲实例化的对象以字节流的形式保存起来。
+ 作用：
	+ 保存持久化对象
	+ 用于远程方法调用，或在网络中传递对象

+ 实现Serializable接口



		public class Persion implements Serializable{
			private String name;
			private Integer age;
			private String gender;
	
			public Person(Sstring name,Integer age,String gender){
			
				this.name=name;
				this.age=age;
				this.gender=gender;
			}
	
			public static void main(String[] args) throws Exception{
				File file=new File("person.out");
				
				ObjectOutputStream out=new ObjectOutputStream(new FileOutputStream(file));
				
				Person person =new Person("John",20,"Male");
				out.writeObject(person);
				out.close();
			}
		}

---

##java内存堆栈
+ 一些基本类型变量和对象的引用在栈中内存分配
+ new创建的对象和数组放在堆里
+ 堆中内存由虚拟机自动垃圾回收器管理
+ 栈中变量指向堆中的变量，就是java的指针
+ 
###堆&&栈
+ 堆：是一个经过排序的树形队列，如二叉堆。根节点的值最小
+ C中：区别就是申请方式不同
	+ 栈中分配局部变量，由系统分配，速度快
	+ 方法调用在栈中
	+ 堆中分配程序员申请的内存空间（malloc）
	
	

---

##equals ==
+ 对于值比较的是大小
+ 对于对象表示是否指向同一块内存
+ String重写了该方法，比较的大小
