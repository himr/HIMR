----------------------------------------
# Task1. MySQL_elementary

## 1.1 MySQL软件及数据库基础

### 1.软件安装及服务器设置。
   教程 [http://www.runoob.com/mysql/mysql-install.html](http://www.runoob.com/mysql/mysql-install.html)

### 2.(选做，但是强烈建议) 使用图形界面软件 Navicat for SQL
  知识星球提供破解版Navicat for SQL，请大家自行查找。
   简易步骤:
      解压缩文件，复制key
      打开文件夹中的navicat.e
      用户名随意，输入key，然后连接数据库
      输入密码，连接名改成自己喜欢的
      剩下的自己探索，怎么在navicat中创建数据库、表等等

### 3.数据库基础知识
   数据库定义:database，保存有组织的数据的容器，通常是或一组文件。
   关系型数据库：建立在关系模型基础上的数据库。
   二维表：某种特定类型数据的结构化清单。
   行：row，表中的记录。
   列：column，表中的字段，纵向。
   主键：一列，其值能够唯一标识表中的每一行。
   外键：确定另一张表记录的字段，用于保持数据的一致性，与另一张表关联。

### 4.MySQL数据库管理系统
   数据库
   数据表：表是数据在数据库中逻辑上的存储形式，与电子表格类似，每行代表记录，每列代表一个字段。
   视图：存储查询语句，当调用时产生结果集，试图充当的是需虚拟表的角色。
   存储过程：数据库中存储复杂程序，以便外部程序调用的一种数据库对象。

----------------------------------------
## 1.2 MySQL基础（一）-查询语句

### 1.导入示例数据库

教程：[https://www.yiibai.com/mysql/how-to-load-sample-database-into-mysql-database-server.html](https://www.yiibai.com/mysql/how-to-load-sample-database-into-mysql-database-server.html)

### 2.SQL是什么？ MySQL是什么？

### 3.查询语句 SELECT FROM
  语句解释：读取一条或多条记录。
  SELECT coulunm_name,column_name
  FROM table_name
  [WHERE Clause]
  [LIMIT N][ OFFSET M]
  
  去重语句：
  前N个语句
  CASE...END 判断语句
  
### 4.筛选语句 WHERE
  语句解释:有条件地从表中选择数据
  SELECT field1, field2,...fieldN FROM table_name1, table_name2...
  [WHERE condition [AND [OR]] condition2...]
  
  运算符/通配符/操作符
  
### 5.分组语句 GROUP BY
  聚集函数：COUNT, SUM, AVG等
  语句解释：根据一或多个列对结果进行分组。
  HAVING子句
  
### 6.排序语句 ORDER BY
  语句解释
  正序、逆序
  
### 7.函数
  时间函数
  数值函数
  字符串函数
  
### 8.SQL注释

### 9.SQL代码规范

--------------------------------------
## 项目一

查找重复的电子邮箱（难度：简单）
创建 email表，并插入如下三行数据
+----+---------+
| Id | Email   |
+----+---------+
| 1  | a@b.com |
| 2  | c@d.com |
| 3  | a@b.com |
+----+---------+

编写一个 SQL 查询，查找 Email 表中所有重复的电子邮箱。
根据以上输入，你的查询应返回以下结果：
+---------+
| Email   |
+---------+
| a@b.com |
+---------+
说明：所有电子邮箱都是小写字母。
--------------------------------------
-- 创建表
CREATE TABLE email (
ID INT NOT NULL PRIMARY KEY,
Email VARCHAR(255)
);
-- 插入数据
INSERT INTO email VALUES('1','a@b.com');
INSERT INTO email VALUES('2','c@d.com');
INSERT INTO email VALUES('3','a@b.com');

--------------------------------------

## 项目二

查找大国（难度：简单）
创建如下 World 表
+-----------------+------------+------------+--------------+---------------+
| name            | continent  | area       | population   | gdp           |
+-----------------+------------+------------+--------------+---------------+
| Afghanistan     | Asia       | 652230     | 25500100     | 20343000      |
| Albania         | Europe     | 28748      | 2831741      | 12960000      |
| Algeria         | Africa     | 2381741    | 37100000     | 188681000     |
| Andorra         | Europe     | 468        | 78115        | 3712000       |
| Angola          | Africa     | 1246700    | 20609294     | 100990000     |
+-----------------+------------+------------+--------------+---------------+
如果一个国家的面积超过300万平方公里，或者(人口超过2500万并且gdp超过2000万)，那么这个国家就是大国家。
编写一个SQL查询，输出表中所有大国家的名称、人口和面积。
例如，根据上表，我们应该输出:
+--------------+-------------+--------------+
| name         | population  | area         |
+--------------+-------------+--------------+
| Afghanistan  | 25500100    | 652230       |
| Algeria      | 37100000    | 2381741      |
+--------------+-------------+--------------+

---------------------------------------

-- 创建表
CREATE TABLE World (
name VARCHAR(50) NOT NULL,
continent VARCHAR(50) NOT NULL,
area INT NOT NULL,
population INT NOT NULL,
gdp INT NOT NULL
);
-- 插入数据
INSERT INTO World
  VALUES('Afghanistan','Asia',652230,25500100,20343000);
INSERT INTO World 
  VALUES('Albania','Europe',28748,2831741,12960000);
INSERT INTO World 
  VALUES('Algeria','Africa',2381741,37100000,188681000);
INSERT INTO World
  VALUES('Andorra','Europe',468,78115,3712000);
INSERT INTO World
  VALUES('Angola','Africa',1246700,20609294,100990000);
  
