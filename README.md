## 基本操作(crud)

### `select`
##### SELECT 语句用于从数据库中选取数据
- SELECT column_name,column_name FROM table_name;
- SELECT * FROM table_name;

### `select distinct`
##### SELECT DISTINCT 语句用于返回唯一不同的值
- SELECT DISTINCT column_name,column_name FROM table_name;

### `where`
##### WHERE 子句用于过滤记录
- SELECT column_name,column_name FROM table_name WHERE column_name operator value;

### `and&or`
##### AND & OR 运算符用于基于一个以上的条件对记录进行过滤

### `order by`
##### ORDER BY 关键字用于对结果集进行排序
- SELECT column_name,column_name FROM table_name ORDER BY column_name,column_name ASC|DESC;

### `insert into`
##### INSERT INTO 语句用于向表中插入新记录
- INSERT INTO table_name VALUES (value1,value2,value3,...);
- INSERT INTO table_name (column1,column2,column3,...) VALUES (value1,value2,value3,...);

### `update`
##### UPDATE 语句用于更新表中的记录
- UPDATE table_name SET column1=value1,column2=value2,... WHERE some_column=some_value;

### `delete`
##### DELETE 语句用于删除表中的记录
- DELETE FROM table_name WHERE some_column=some_value;

## 函数

### `avg()`
##### AVG() 函数返回数值列的平均值
- SELECT AVG(column_name) FROM table_name

### `count()`
##### COUNT() 函数返回匹配指定条件的行数
- SELECT COUNT(column_name) FROM table_name;

### `max()`
##### MAX() 函数返回指定列的最大值
- SELECT MAX(column_name) FROM table_name;

### `min()`
##### MIN() 函数返回指定列的最小值
- SELECT MIN(column_name) FROM table_name;

### `sum()`
##### SUM() 函数返回数值列的总数
- SELECT SUM(column_name) FROM table_name;

### `group by`
##### GROUP BY 语句可结合一些聚合函数来使用
- SELECT column_name, aggregate_function(column_name) FROM table_name WHERE column_name operator value GROUP BY column_name;

### `having`
##### 在 SQL 中增加 HAVING 子句原因是，WHERE 关键字无法与聚合函数一起使用。

### `exists`
##### EXISTS 运算符用于判断查询子句是否有记录，如果有一条或多条记录存在返回 True，否则返回 False。
- SELECT column_name(s) FROM table_name WHERE EXISTS (SELECT column_name FROM table_name WHERE condition);

### `ucase()`
##### UCASE() 函数把字段的值转换为大写。
- SELECT UCASE(column_name) FROM table_name;

### `lcase()`
##### LCASE() 函数把字段的值转换为小写。
- SELECT LCASE(column_name) FROM table_name;

### `mid()`
##### MID() 函数用于从文本字段中提取字符
- SELECT MID(column_name,start,length) FROM table_name;

### `len()`
##### LEN() 函数返回文本字段中值的长度
- SELECT LEN(column_name) FROM table_name;

### `round()`
##### ROUND() 函数用于把数值字段舍入为指定的小数位数
- SELECT ROUND(column_name,decimals) FROM TABLE_NAME;

### `now()`
##### NOW() 函数返回当前系统的日期和时间。
- SELECT NOW() FROM table_name;

### `format()`
##### FORMAT() 函数用于对字段的显示进行格式化
- SELECT FORMAT(column_name,format) FROM table_name;

## 高级操作

### `like`
##### LIKE 操作符用于在 WHERE 子句中搜索列中的指定模式
- SELECT column_name(s) FROM table_name WHERE column_name LIKE pattern;

### `in`
##### IN 操作符允许您在 WHERE 子句中规定多个值
- SELECT column_name(s) FROM table_name WHERE column_name IN (value1,value2,...);

### `between`
##### BETWEEN 操作符用于选取介于两个值之间的数据范围内的值
- SELECT column_name(s) FROM table_name WHERE column_name BETWEEN value1 AND value2;

### `join`
##### join 用于把来自两个或多个表的行结合起来
- INNER JOIN：如果表中有至少一个匹配，则返回行
- LEFT JOIN：即使右表中没有匹配，也从左表返回所有的行
- RIGHT JOIN：即使左表中没有匹配，也从右表返回所有的行
- FULL JOIN：只要其中一个表中存在匹配，则返回行

### `inner join`
##### INNER JOIN 关键字在表中存在至少一个匹配时返回行,INNER JOIN 与 JOIN 是相同的。
- SELECT column_name(s) FROM table1 INNER JOIN table2 ON table1.column_name=table2.column_name;
- SELECT column_name(s) FROM table1 JOIN table2 ON table1.column_name=table2.column_name;

### `left join`
##### LEFT JOIN 关键字从左表（table1）返回所有的行，即使右表（table2）中没有匹配。如果右表中没有匹配，则结果为 NULL。
- SELECT column_name(s) FROM table1 LEFT JOIN table2 ON table1.column_name=table2.column_name;

### `right join`
##### RIGHT JOIN 关键字从右表（table2）返回所有的行，即使左表（table1）中没有匹配。如果左表中没有匹配，则结果为 NULL。
- SELECT column_name(s) FROM table1 RIGHT JOIN table2 ON table1.column_name=table2.column_name;

### `full outer join`
##### FULL OUTER JOIN 关键字只要左表（table1）和右表（table2）其中一个表中存在匹配，则返回行.
- SELECT column_name(s) FROM table1 FULL OUTER JOIN table2 ON table1.column_name=table2.column_name;

### `union`
##### UNION 操作符合并两个或多个 SELECT 语句的结果。
##### 默认地，UNION 操作符选取不同的值。如果允许重复的值，请使用 UNION ALL。
- SELECT column_name(s) FROM table1 UNION SELECT column_name(s) FROM table2;

### `select into`
##### SELECT INTO 语句从一个表复制数据，然后把数据插入到另一个新表中。
- SELECT * INTO newtable [IN externaldb] FROM table1;
- SELECT column_name(s) INTO newtable [IN externaldb] FROM table1;

### `insert into select`
##### INSERT INTO SELECT 语句从一个表复制数据，然后把数据插入到一个已存在的表中。
- INSERT INTO table2 SELECT * FROM table1;
- INSERT INTO table2 (column_name(s)) SELECT column_name(s) FROM table1;

### `create database`
##### CREATE DATABASE 语句用于创建数据库。
- CREATE DATABASE dbname;

### `create table`
##### CREATE TABLE 语句用于创建数据库中的表。
- CREATE TABLE table_name (column_name1 data_type(size),column_name2 data_type(size),column_name3 data_type(size),....);

### `Constraints`
#####  约束用于规定表中的数据规则。
- CREATE TABLE table_name
(
column_name1 data_type(size) constraint_name,
column_name2 data_type(size) constraint_name,
column_name3 data_type(size) constraint_name,
....
);

### `not null`
##### NOT NULL 约束强制列不接受 NULL 值。

### `unique`
##### UNIQUE 约束唯一标识数据库表中的每条记录。
##### UNIQUE 和 PRIMARY KEY 约束均为列或列集合提供了唯一性的保证。
##### PRIMARY KEY 约束拥有自动定义的 UNIQUE 约束。
##### 请注意，每个表可以有多个 UNIQUE 约束，但是每个表只能有一个 PRIMARY KEY 约束。

### `primary key`
##### PRIMARY KEY 约束唯一标识数据库表中的每条记录。
##### 主键必须包含唯一的值。
##### 主键列不能包含 NULL 值。
##### 每个表都应该有一个主键，并且每个表只能有一个主键。

### `foreign key`
##### 一个表中的 FOREIGN KEY 指向另一个表中的 UNIQUE KEY(唯一约束的键)。

### `check`
##### CHECK 约束用于限制列中的值的范围。
##### 如果对单个列定义 CHECK 约束，那么该列只允许特定的值。
##### 如果对一个表定义 CHECK 约束，那么此约束会基于行中其他列的值在特定的列中对值进行限制。

### `default`
##### DEFAULT 约束用于向列中插入默认值。

### `create index`
##### CREATE INDEX 语句用于在表中创建索引。
- CREATE INDEX index_name ON table_name (column_name);

### `drop`
##### 通过使用 DROP 语句，可以轻松地删除索引、表和数据库。

### `alter`
##### ALTER TABLE 语句用于在已有的表中添加、删除或修改列。

### `auto increment`
##### Auto-increment 会在新记录插入表中时生成一个唯一的数字。

### `views`
##### 在 SQL 中，视图是基于 SQL 语句的结果集的可视化的表。

### `date`
##### 当我们处理日期时，最难的任务恐怕是确保所插入的日期的格式，与数据库中日期列的格式相匹配。

### `null`
##### NULL 值代表遗漏的未知数据。
- SELECT LastName,FirstName,Address FROM Persons WHERE Address IS NULL;
- SELECT LastName,FirstName,Address FROM Persons WHERE Address IS NOT NULL;

### `null函数`
##### SQL ISNULL()、NVL()、IFNULL() 和 COALESCE() 函数
