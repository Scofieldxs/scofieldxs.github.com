###practice


####获得当天日期

	dateTime=$(date +%Y%m%d)

####得到一个数字序列

	seq 1 10      # =(1-10)
	for i in $(seq 1 10)   #与for合用

####整数运算

	let s=2+4*3


####取出/etc/passwd文件中shell出现的次数

	cat /etc/passwd | awk -F: '{print $7}' |sort|uniq -c

####合并文件


employee.txt:  

100 Jason Smith   

200 John Doe   

300 Sanjay Gupta 

bonus.txt:  

100 $5,000   

200 $500   

300 $3,000   

	paste employee.txt bonus.txt | awk '{print $1,$2,$3,$5}' | sort -k 2
+ paste：按行进行合并

+ sort -k 2：按第2列进行排序



​
####替换：将test.txt中第2行的if替换为fi

	sed -i '2s/if/fi/g'test.txt
+ s/替换前/替换后/g 


####查看指定行列

	sed -n '2p' employee.txt | cut -d " " -f1
+ 显示文件第2行第1列 