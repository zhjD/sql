# sql
## 1. DDL数据库创建语言 CREATE ALTER DROP
## 2. DML数据库管理语言 SELECT 查询
### 单表查询

#### 1.输出列

###### 指定列的别名
    SELECT LEFT(Ename,1) AS 姓  # 可以使用函数 LEFT
        FROM EmpLoyee

###### 计算输出列
    SELECT Eno+'--'+Ename+'('+Sex+')' As 职工
        FROM Eemployee

#### 2.输出行
##### 输出无重复行
    SELECT DISTINCT Title
        FROM Employee

##### 输出前n行（百分比）数据
    SELECT TOP 2 * FROM Employee
        SELECT TOP 30 PERCENT * FROM Employee

#### 3.带条件的查询--WHERE子句
##### 比较运算符
    SELECT * FROM Item
         WHERE YEAR(End_date)<'2020' # 年份小于2020

##### 特殊运算符
![image](https://user-images.githubusercontent.com/89053711/147112475-e33097e0-b188-4584-a07a-bd4fca0cd4d0.png)

     SELECT Ename From Employee
         WHERE Title in ('高工'，'工程师')
---
    
    SELECT * FROM Salary 
	      WHERE Basepay NOT BETWEEN 500 AND 700;
---
    SELECT * FROM Item 
	      WHERE Check_date IS NOT NULL;
---
LIKE运算符的用法

    [NOT]  LIKE  '<匹配字符串>' # 通配符 %(任意长度字符), _(单个字符) 
---
    SELECT Iname FROM Item
	      WHERE Iname LIKE '%性能研究%';
##### 多条件单关系查询
    SELECT *
	      FROM Salary 
	      WHERE (Basepay BETWEEN 600 AND 700 ) 
        AND ( Service IN (600.0,700.0,1300.0,2500.0) )
        AND Eno LIKE '100_';
##### 分组查询









