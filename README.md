# mysql表操作

#### 表的含义
> mysql采用表的形式存储数据
#### sql结构化查询语言
> sql是访问和处理数据的标准计算机语言
#### sql语言分类
> DML|DCL|DDL的用途
#### 特定名词解释
> 表、字段、主键、外键、约束、索引
#### sql表的操作语句
> 使用sql完成表的新建、修改、删除操作
#### 数据库的三范式
> 理解数据库的三范式的特点与区别

# sql的基本查询

#### sql中select语句
> select语句基本形式
#### mysql中分页处理
> 对数据实现分页查询
#### 对数据排序
> order by子句用法
#### 数据去重
> distinct关键字的使用办法
#### 条件查询
> where子句的书写细节

# sql高级查询

#### 聚合函数的用途
> avg、max、count等聚合函数使用
#### 分组查询
> group by、having子句的用途与书写
#### 表连接查询
> 多表内连接、左连接、右连接的写法
#### 子查询
> 子查询不同场景下的应用

# sql写入操作

#### insert语句
> 利用sql语法insert into实现数据插入
#### update语句
> 利用sql语法update实现数据更新
#### delete语句
> 利用sql语法delete实现数据删除

# sql基本函数

#### mysql数字函数
> format、abs、mod
#### mysql字符函数
> upper、lower、char_length
#### 日期与条件函数
> now、date_format

***

# 数据库表的基本操作
#### sql语句注意事项
> sql语句不区分大小写，但是字符串区分大小写  
> sql语句必须以分号结尾  
> sql语句中的空白和换行没有限制，但是不能破坏语法  
#### 创建逻辑库
> mysql > CREATE DATABASE 逻辑库名称;  
> mysql > SHOW DATABASES;  
> mysql > DROP DATABASE 逻辑库名称;  
#### 创建数据表
> CREATE TABLE 数据表（  
>   列名1 数据类型[约束][COMMENT 注释],  
>   列名2 数据类型[约束][COMMENT 注释],  
>   ······  
> ）[COMMENT=注释];  
> DROP TABLE 数据表;  
#### 数据表的其他操作
> SHOW table;  
> DESC student;  
> SHOW CREATE TABLE student;  
> DROP TABLE student;  
#### 添加字段
> ALTER TABLE 表名称  
> ADD 列1 数据类型[约束][COMMENT 注释],  
> ADD 列1 数据类型[约束][COMMENT 注释],  
> ······;  
#### 修改字段类型和约束
> ALTER TABLE 表名称  
> MODIFY 列1 数据类型[约束][COMMENT 注释],  
> MODIFY 列2 数据类型[约束][COMMENT 注释],  
> ······;  
#### 修改字段名称
> ALTER TABLE 表名称  
> CHANGE 列1 新列名1 数据类型[约束][COMMENT 注释],  
> CHANGE 列2 新列名2 数据类型[约束][COMMENT 注释],  
> ······;  
#### 删除字段
> ALTER TABLE 表名称  
> DROP 列1,  
> DROP 列2,  
> ······;  
#### 修改表名
> ALTER TABLE 表名 RENAME 新表名;  
#### 如何创建索引
> CREATE TABLE 表名称（  
>   ······,  
>   INDEX[索引名称](字段)  
>   ······  
> ）;  
#### 如何添加与删除索引
> CREATE INDEX 索引名称 ON 表名(字段);  
> ALTER TABLE 表名称 ADD INDEX [索引名](字段);  
> SHOW INDEX FROM 表名;  
> DROP INDEX 索引名称 ON 表名;  
#### 索引的使用原则
> 数据量很大，而且经常被查询的数据表可以设置索引  
> 索引只添加在经常被用作检索条件的字段上面  
> 不要在大字段上创建索引  

***

# 数据库的基本查询
#### 记录查询
> 最基本的查询语句是由SELECT和FROM关键字组成的  
> ```
> SELECT * FROM t_student;  
> SELECT id,name,sex FROM t_student;  
> ```
#### 使用列别名
> 通常情况下，SELECT子句中使用了表达式，那么这列的名字就默认为表达式，因此需要一种对列名重命名的机制  
> ```
> SELECT  
>   ename,  
>   sal *12 AS "annual_salary"  
> FROM  
>   emp;  
> ```
#### 数据分页
> 如果结果集的记录很多，则可以使用LIMIT关键字限定结果集数量。  
> ```
> SELECT ······FROM ······LIMIT起始位置，偏移量；
> SELECT empno,ename FROM t_emp LIMIT 0,20;
> ```
#### 结果集排序
>```
>SELECT ··· FROM ··· ORDER BY 别名 [ASC|DESC];
>SELECT ename,sal FROM t_emp ORDER BY sal;
>```
#### 去除重复记录
> 如果需要去除重复的数据，可以使用DISTINCT关键字来实现
> SELECT DISTINCT 字段 FROM ···;
> ```
> SELECT DISTINCT job FROM t_emp;
> ```
#### 条件查询
> SELECT ... FROM ... WHERE 条件 [AND|OR]条件...;
> ```
> SELECT empno,ename,sal FROM t_emp  
> WHERE deptno=10 AND sal>=2000;  
> ```
