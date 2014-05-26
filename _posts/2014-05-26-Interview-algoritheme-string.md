---
layout: post
title: algorithme1
cover: cover_3.jpg
date:   2014-05-26 12:00:00
categories: posts
---
<br/>
<br/>
##字符串
###旋转问题
####1.左旋字符串
+ abcdefghi---左旋三个--->defghiabc
+ 思路：左旋m位就以m为单位进行交换：
	+ abcdefghi-->defabcghi
	+ defabcghi-->defghiabc
	+ 若最后有剩余，将最后的几位前移m位：
	+ defghi abcj-->defghi abjc-->defghi ajbc-->defghi jabc

###包含问题
####1.两个字符串，短的元素是否都包含在长的里面
>
> 思路：对长的建立hash表，在相应位置标记为true，看短的是否在hash表中

####2.求两个字符串的最小编辑距离，可进行插入、删除、替换操作
思路：动态规划：dis[i,j]表示s1前i个字符和s2前j个字符的距离

若s1[i]==s2[j]：dis[i,j]=dis[i-1,j-1]

否则：dis[i,j]=min(dis[i,j-1]+1,dis[i-1,j]+1,dis[i-1,j-1]+2)


----

###有多少中组合问题
####1.输入一个字符串，打印字符串所有排列
思路：递归实现：从集合中一次选出一个元素作为首元素，对其余进行全排列

	void CalAll(char perm[],int first,int num)
	{
		...//跳出判断
		for(int i=first,i<first+num;i++)
		{
			swap(perm[i],perm[first]);
			CallAll(perm,first+1,num-1);
			swap(perm[i],perm[first]);
		}
	}

####2.n个台阶，一次可以跳1、2、3级，多少中跳法
思路：找关系,类似斐波那契数列

		f(n)=1    n=1
		f(n)=2    n=2
		f(n)=4    n=3
		f(n)=f(n-1)+f(n-2)+f(n-3)    n>3
	
