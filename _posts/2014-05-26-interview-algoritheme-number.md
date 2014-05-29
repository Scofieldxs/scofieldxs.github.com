---
layout: post
title: algorithme
cover: cover_3.jpg
date:   2014-05-26 12:00:00
categories: posts
---
<br/>
<br/>
##数字
###查找
####1.n个元素中查找最小的k个
> 思路：构建k个元素的大根堆，最大元素的根节点，如果下一个元素比它小，则替换，然后更新最大堆
> 
> 思路2：类似快排的思路：将数组S划分为Sa和Sb
> 
> 如果k<Sa，返回Sa,然后在Sb中查找k-Sa.length个元素

>如果k>Sa,对Sa进行划分

####2.寻找和为定值的两个数
>思路：排序，两个指针i，j分别从头尾遍历：

>若a[i]+a[j]==m：找到

>若a[i]+a[j]<m：i++

>a[i]+a[j]>m：j--

####3.从数列1,2,3...n中随机选择n个数使其等于m，求所有组合
>对于其中一个数字，包括取i，不取i两种情况，因此用背包：

		void find_factor(int sum,int n)
		{
			if(sum==n)
			{
				...//找到一个满足的打印list
			}
			list1.push_front(n);
			find_factor(sum-n,n-1);
			list1.pop_front();
			find_factor(sum,n-1);
		}


+ 总结：对类似求所有组合的题，可以考虑背包算法
####4.求500万以内的亲合数
>亲合数：若两个数a,b，a的所有因数之和=b,b的所有因数之和=a，则a,b为一对亲合数

>思路：使用伴随数组：sum[5000000]，把1-2500000所有下标为i的倍数的位置加i，则sum[i]表示数字i的所有因数之和

+ 总结：伴随数组的思路，就是以空间换时间


####5.一个数组中有一个数字出现的次数大于数组长度的一半，找出来这个数
思路1：快排，中间的那个数就是要找的 O(nlogn)

思路2：遇到两个不同的数就删除，剩下的就是要找的

思路3：记录一组key,value。
>key相同：value+1

>key不同：value-1

>value等于0，下一个值设为key,value=1

###求构成最大条件的子集合
####1.求子数组的最大和
>思路：求前几个数的和b，若b小于0，则将b重新赋值为下一个数，

>若b>sum，更新sum=b

####2.最长公共子序列
>子序列：可以不连续；子串：连续的

>思路：动态规划：

>c[i,j]=0    i=0 or j=0

>c[i,j]=c[i-1,j-1]+1  x[i]==y[j]

>c[i,j]=max(c[i,j-1],c[i-1,j])  


####3.求最大乘积连续子串的值，有正负零
思路：动态规划，需要维护两个量：最小和最大：

maxA[i]=max(max(a[i],maxA[i-1]*a[i]),minA[i-1]*a[i])
minA[i]=min(min(a[i],minA[i-1]*a[i]),maxA[i-1]*a[i])

---

###排序
####1.一个文件有小于n个数，且大小<n(10^7),排序，内存1MB
>思路：位图法：对于数i对应的比特位置为1

bitset<50000000> bit_map;
bit_map.set(num,1);

>思路2：
>
>1.每次读取一部分进行排序，形成n个文件

>2.从n个文件中读取最小的数放入数组data[n]

>3.选择最小的写入result，更新data

+ 总结：大数据排序：位图或者多路归并


####2.一个未排序数组有正负，重新排列使负数在正数前面，并且保持原来相对顺序
思路：从后往前找到第一个负数，在该负数左侧探测正数块，交换负数块与正数块