### 数据库（database）
定义：保存有组织的数据的容器（通常是一个文件或一组文件）。
### 表（table）
定义：某种特定类型数据的结构化清单。
表名的唯一性：在相同的数据库中不能有2个相同的表名。
### 列（column）
定义：表中的一个字段，所有表都是由一个或多个列组成。
### 数据类型（datatype）
定义：所容许的数据的类型。每个表列都有相应的数据类型，它限制或容许该列中存储的数据。
### 行（row）
定义：表中的一个记录。
### 主键（primary key）
定义：一列（或一组列），其值能够唯一区分表中每个行。
主键满足的条件：
* 任意两行都不具有相同的主键值；
* 每个行都必须具有一个主键值（主键列不允许NULL值）。

主键的最好习惯：
* 不更新主键列中的值；
* 不重用主键列的值；
* 不在主键列中使用可能会更改的值。