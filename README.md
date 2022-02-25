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

### `union`












## 函数


































































