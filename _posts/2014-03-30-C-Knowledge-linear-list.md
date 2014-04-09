---
layout: post
title: C Knowledge-linear list
cover: 1166365595121c5dc7l.jpg
date:   2013-12-09 12:00:00
categories: posts
---
<br/>
<br/>
C Knowledge:linear list
===
<br/>
<br/>
>线性表是一种逻辑结构

>顺序表和链表是指存储结构，属于不同层面的概念

<br/>
<br/>
##顺序表
+ 顺序表：有一定维护数据的数组，最主要特点：随机存储
+ 数据结构：

		typedef struct{
				ElemType *data;
				int MaxSize,length;
			}SeqList;
+ 插入:

		bool ListInsert(SeqList &L,int i,ElemType e)
		{
		if(i<1||i>L.length)
		{
			return false;
		}
		if(L.length>=L.MaxSize)
		{
			return false;
		}
	
		for(int j=L.length;j>=i;j--)
		{
			L.data[j]=L.data[j-1];
		}
		L.data[i-1]=e;//i-1位置插入
		L.length++;
		return true;
		}

<br/>
##单链表
+ 数据结构 

			typedef struct LNode{
				ElemType data;
				struct LNode *next;
			}LNode,*LinkList;
+ 用头指针L标示单链表，L=NULL时表示空
+ 头插入创建链表

			LinkList CreateList(LinkList &L)
			{
				L=(LinkList)malloc(sizeof(LNode));
				L->next=NULL;
			
				int x;
				scanf("%d",&x);
				while(x!=9999)
				{
					LNode *s=(LNode *)malloc(sizeof(LNode));
					s->data=x;
					s->next=L->next;
					L->next=s;
			
					scanf("%d",&x);
				}
				return L;
			}

##双链表
+ 数据结构

		typedef struct DNode{
			ElemType data;
			struct DNode *prior,*next;
			}DNode,*DLinklist;

+ 插入（s插入到p后）

		bool Insert(DNode *s,DNode *p)
		{
			s->next=p->next;
			p->next->prior=s;
			s->prior=p;
			p->next=s;
		}