---
layout: post
title: 数据库 插入操作
cover: cover_5.jpg
date:   2014-06-10 12:00:00
categories: posts
---
<br/>
<br/>

###数据库查询操作

---

**employee表：**

employee_id

name

salary

manager_id

department_id

**department表：**

dempartment_id

manager_id

location_id

**1.查询出name为 ‘Chen’ 的 manager 的信息**



	select m.*	
	from employee e,employee m	
	where m.employeeid=e.manager_id and e.name='chen'


**2.查询平均工资高于 8000 的部门 id 和它的平均工资.**

	select department_id,avg(salary)	
	from employee 
	group by department_id	
	having avg(salary)>8000

**3.查询工资最低的员工信息**

	select name,salary	
	from employee	
	where salary=(	
		select min(salary)
		from employee
	)


**4.查询平均工资最低的部门信息**
	
	select * 
	from department
	where department_id=(
		select department_id
		from employee
		group by department_id
		having avg(salary)=(
			select min(ave(salary))
			from employee
			group by department_id
			)
		)

**5.查询出公司中所有 manager 的详细信息**

	select * 
	from employee
	where employee_id in(
		select distinct manager_id
		from employee
		)