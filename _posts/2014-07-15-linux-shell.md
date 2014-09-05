---
layout: post
title: linux-shell
cover: cover_5.jpg
date:   2014-07-07 12:00:00
categories: posts
---
###linux shell script
####判断参数是否为空

	if [ ! -n "$1" ];then

####判断参数是否为数字

	test=$( echo $first | grep '[0-9]')
	if [ ! -n "$test" ];then
		//error
	fi

####快捷键
左移h、右移l、下移j、上移k
移动到行尾：$
下一行插入：o
删除当前字符：x

####删除文件及子文件：

	rm -r filename