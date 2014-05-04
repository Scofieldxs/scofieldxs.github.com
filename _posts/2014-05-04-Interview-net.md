---
layout: post
title: 面试：网络
cover: cover_1.jpg
date:   2014-05-04 12:00:00
categories: posts
---
<br/>
<br/>

Interview:net
===

---

### 五层结构：
	1. 应用层
	2. 运输层：TCP UDP
	3. 网络层:IP
	4. 链路层:MAC,交换机
	5. 物理层

---

###  MAC
	+ 6B长，48bit，6个十六进制数表示

---
### IP
	+ 三级结构：<网络号，子网号，主机号>
	+ 网络地址=IP & 子网掩码

---
### 协议
	1. ARP：完成IP地址到MAC地址映射，工作在网络层
	2. DHCP：动态主机配置协议，工作在应用层，基于UDP
	3. ICMP：网际控制报文协议，用于主机或路由报告差错或异常，网络层协议
	4. PING:工作在应用层，直接使用ICMP，而非TCP
	5. traceroute:工作在网络层，使用ICMP

---
### 端口
	+ 16bit
	+ 服务端使用端口：
		+ 0-1023：熟知端口
		+ 1024-49151：

	+ 客户端：49152-65536：动态选择

---

### 三次握手：
	1. -- SYN=1，seq=x -->
	2. <- SYN=1,ACK=1,seq=y,ack=x+1 --
	3. -- ACK=1,seq=x+1,ack=y+1 -->

### 四次关闭：
	1. -- FIN=1,seq=u -->
	2. <- ACK=1,seq=v,ack=u+1--
	3. <- FIN=1,ACK=1,seq=w,ack=u+1--
	4. -- ACK=1,seq=u+1,,ack=w+1 -->