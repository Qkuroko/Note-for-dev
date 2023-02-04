# SQL语句

### 1、DDL

​				数据定义语言，用来定义数据库对象(数据库，表，字段)	

```sql
		#一数据库操作 创销增删改查
        #1、创
        	create database [ if not exists ] 数据库名 [ default charset 字符集 ] [collate 排序则 ]
        #2、销
        	drop database [ if exists ] 数据库名
        #3、查 （增删略)
        	#1、查询所有数据库 
        		show databases;
        	#2、查询当前数据库
        		select database();
        #4、切换数据库
        	use 数据库名 ;
        
        
        
        
        
        #二、表操作
        	#创表
        	CREATE TABLE 表名(
				字段1 字段1类型 [ COMMENT 字段1注释 ],
                ......
                字段n 字段n类型 [COMMENT 字段n注释 ]
            ) [ COMMENT 表注释 ] ;
            #2、销表
            DROP TABLE [ IF EXISTS ] 表名;
            #3、改
            	#1)添加字段
            	ALTER TABLE 表名 ADD 字段名 类型 (长度) [ COMMENT 注释 ] [ 约束 ];
            	#2)修改数据类型
            	ALTER TABLE 表名 MODIFY 字段名 新数据类型 (长度);
            	#3)修改字段名和字段类型
            	ALTER TABLE 表名 CHANGE 旧字段名 新字段名 类型 (长度) [ COMMENT 注释 ] [ 约束 ];
            	ALTER TABLE emp CHANGE nickname username varchar(30) COMMENT '昵称';
        		#4)删除字段
        		ALTER TABLE 表名 DROP 字段名;
        		#修改表名
        		ALTER TABLE emp RENAME TO employee;
        	#4、查
        		#1)查当前数据库所有表
        		show tables;
        		#2)查看指定表结构
        		desc 表名 ;
        		
        		
```



### 2、DML 

​				数据操作语言，用来对数据库表中的数据进行增删改

**添加数据（INSERT）**

**删除数据（DELETE）**

**修改数据（UPDATE）**

SELECT

​	字段列表

FROM

​	表名列表

WHERE

​	条件列表

GROUP BY

​	分组字段列表

HAVING

​	分组后条件列表

ORDER BY

​	排序字段列表

LIMIT

​	分页参数



```sql

#1.给指定字段添加数据
	INSERT INTO 表名 (字段名1, 字段名2, ...) VALUES (值1, 值2, ...);
	INSERT INTO 表名 VALUES (值1, 值2, ...);
	INSERT INTO 表名 (字段名1, 字段名2, ...) VALUES (值1, 值2, ...), (值1, 值2, ...), (值1, 值2, ...) ;
	INSERT INTO 表名 VALUES (值1, 值2, ...), (值1, 值2, ...), (值1, 值2, ...) ;
#2.删
	DELETE FROM 表名 [ WHERE 条件 ] ;  eg: delete from employee where gender = '女';
	delete from employee;#删除所有员工
#3.改
	UPDATE 表名 SET 字段名1 = 值1 , 字段名2 = 值2 , .... [ WHERE 条件 ] ;
	update employee set name = '小昭' , gender = '女' where id = 1;
```



### 3、DQL

​				数据查询语言，用来查询数据库中表的记录

基本查询（不带任何条件）

条件查询（WHERE）

聚合函数（count、max、min、avg、sum）

分组查询（group by）

排序查询（order by）

分页查询（limit）

```sql
#基础查询
	#1).查询多个字段
	SELECT * FROM 表名 ;#低效不常用
	SELECT 字段1, 字段2, 字段3 ... FROM 表名 ;
	#2)查询设置别名
	SELECT 字段1 [ 别名1 ] , 字段2 [ 别名2 ] ... FROM 表名;
	#3).去除重复记录
	SELECT DISTINCT 字段列表 FROM 表名;
```

 条件查询

```sql
#基础语法	
	SELECT 字段列表 FROM 表名 WHERE 条件列表 ; \
	

#特殊用法
	select * from emp where age in(18,20,40);
	select * from emp where idcard like '%X';# %" 表示任意n个字符
	select * from emp where name like '__';# "_" 表示任意一个字符
	
```

聚合函数

count  max min avg sum

```sql
#将一列数据作为一个整体，进行纵向计算
	SELECT 聚合函数(字段列表) FROM 表名 ;
	select count(*) from emp; -- 统计的是总记录数
	select count(idcard) from emp; -- 统计的是idcard字段不为null的记录数
	
	select sum(age) from emp where workaddress = '西安'; -- 统计西安地区员工的年龄之和
```

**分组查询**

where与having区别

执行时机不同：where是分组之前进行过滤，不满足where条件，不参与分组；而having是分组之后对结果进行过滤。

判断条件不同：where不能对聚合函数进行判断，而having可以。

```sql
#基础语法
	SELECT 字段列表 FROM 表名 [ WHERE 条件 ] GROUP BY 分组字段名 [ HAVING 分组后过滤条件 ];
	
#eg:
	#查询年龄小于45的员工 , 并根据工作地址分组 , 获取员工数量大于等于3的工作地址
	select workaddress, count(*) 工作地址统计 from emp where age<45 group by workaddress
	having  工作地址统计>=3;#取别名
#统计各个工作地址上班的男性及女性员工的数量	
	select workaddress,gender,count(*) from emp group by gender,workaddress;
```

#### 排序查询

ASC : 升序(默认值,可省略)  

DESC: 降序

```sql
#基础语法
	SELECT 字段列表 FROM 表名 ORDER BY 字段1 排序方式1 , 字段2 排序方式2 ;
#eg:
	#A. 根据年龄对公司的员工进行降序排序
		select * from emp order by age desc;
	#C. 根据年龄对公司的员工进行升序排序 , 年龄相同 , 再按照入职时间进行降序排序
		select * from emp order by age asc, entrydate desc ;
```

分页查询

​	SELECT 字段列表 FROM 表名 LIMIT 起始索引, 查询记录数 ;   起始索引从0开始

### 4、DCL

​				数据控制语言，用来创建数据库用户、控制数据库的访问权限

