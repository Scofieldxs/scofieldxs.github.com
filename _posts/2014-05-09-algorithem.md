---
layout: post
title: 算法
cover: cover_2.jpg
date:   2014-05-09 12:00:00
categories: posts
---
<br/>
<br/>

Algorithme
===

##动态规划
+ 看是否满足最优子结构：问题的最优解由相关子问题的最优解组合而成。
+ 朴素的递归算法可以实现动态规划的功能，但是效率低下，是因为它反复求解相同的子问题。
+ 动态规划保存子问题结果，随后用到时候直接拿，因此属于用空间换时间
+ 合适用：
	+ 有最优子结构
	+ 子问题重叠

---

##B- B+
+ B-树关键字个数在[m/2(向上取整)-1，m-1]之间。
+ 插入节点超上界则分裂；删除节点若超下界则合并
+ B+树关键字个数在[m/2(向上取整),m]之间
+ B+树中关键字都在叶节点中，非叶节点仅仅是索引。

---

##快排

	int partition(int a[],int low,int high)
	{
		int key=a[low];
		while(low<high)
		{
			while(low<high&&key<a[high]) high--;
			a[low]=a[high];
			while(low<high&&key>a[low])low++;
			a[high]=a[low];
		}
		a[low]=key;
		return low;
	}

	void quick_sort(int a[],int low,int high)
	{
		if(low<high)
		{
			int pos=partition(a,low,high);
			quick_sort(a,low,pos);
			quick_sort(a,pos+1,high);
		}
	}

---

##排序比较
	        平均    最坏    空间复杂度    是否稳定
	快排    nlogn   n^2    o(logn)      否		
	
	堆排    nlogn   nlogn  o(1)         否		
	
	归并    nlogn   nlogn  o(n)         是

---
##贪心
+ 贪心通常自顶向下设计：做出一个选择，然后求解自问题的解
+ 和动态规划不同：进行选择时我们做出当前问题中看起来最优的解，不考虑子问题。