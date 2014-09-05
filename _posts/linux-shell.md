###linux bash
####1.read

	read -p "Please input your name:" named

####2.declare
变量默认字符串类型，若要进行数值运算则要声明类型

	declare -i num  //num声明为整数
	
	declare -r num  //num只读

####3.cat
1. 显示整个文件
2. 创建文件

		cat >1 filename

###文件选取工具
####4.cut
字符串选取

	echo $PATH | cut -d ':' -f 5
以冒号为分隔符，选取第5个

	export | cut -c 12-
整列操作，选取每列12个字符之后的

####5.grep
选取包含关键字的行

	last | grep 'root'

###排序
####6.sort

	cat /etc/passwd | sort -t ':' -k 3
以冒号为分隔符，根据第三列进行排序

####7.uniq

	sort | uniq -c
将排序的数据进行合并，并进行统计


###修改
####8.sed


