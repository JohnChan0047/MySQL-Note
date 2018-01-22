在SELECT语句中，数据根据WHERE子句中指定的搜索条件进行过滤。WHERE子句在表名（FROM子句）之后给出，如下所示：


```
SELECT prod_name, prod_price FROM products WHERE prod_price = 2.50;
```

从products表中检索两个列，但不返回所有行，只返回prod_price值为2.50的行，如下所示:

![](/assets/selectwhere.png)

**WHERE子句的位置** 在同时使用ORDER BY和WHERE子句时，应该让ORDER BY位于WHERE之后，否则将会产生错误。
### WHERE子句操作符

![](/assets/WHERE子句操作符.png)

### 空值检验
在创建表时，表设计人员可以指定其中的列是否可以不包含值。在一个列不包含值时，称其为包含空值NULL。
NULL 无值（no value），它与字段包含0、空字符串或仅仅包含空格不同。
SELECT语句有一个特殊的WHERE子句，可用来检查具有NULL值的列。这个WHERE子句就是IS NULL子句。其语法如下：


```
SELECT prod_name FROM products WHERE prod_price IS NULL;
```

这条语句返回没有价格（空prod_price字段，不是价格为0）的所有产品。

### 组合WHERE子句
为了进行更强的过滤控制，MySQL允许给出多个WHERE子句。这些子句可以两种方式使用：以AND子句的方式或OR子句的方式使用。
**操作符（operator）** 用来联结或改变WHERE子句中的子句的关键字。也称为逻辑操作符（logical operator）。
#### AND操作符
AND 用在WHERE子句中的关键字，用来指示检索满足所有给定条件的行。

```
SELECT prod_id, prod_price, prod_name FROM products WHERE vend_id = 1003 AND prod_price <= 10;
```

#### OR操作符
OR操作符与AND操作符不同，它指示MySQL检索匹配任一条件的行。


```
SELECT prod_name, prod_price FROM products WHERE vend_id = 1002 OR vend_id = 1003;
```
#### 计算次序
 * WHERE可包含任意数目的AND和OR操作符。允许两者结合以进行复杂和高级的过滤;
 * AND在计算次序中优先级更高;
 * 使用圆括号明确地分组相应的操作符
**在WHERE子句中使用圆括号** 任何时候使用具有AND和OR操作符的WHERE子句，都应该使用圆括号明确地分组操作符。不要过分依赖默认计算次序，即使它确实是你想要的东西也是如此。使用圆括号没有什么坏处，它能消除歧义。

#### IN操作符
IN操作符用来指定条件范围，范围中的每个条件都可以进行匹配。IN取合法值的由逗号分隔的清单，全都括在圆括号中。


```
SELECT prod_name, prod_price FROM products WHERE vend_id IN (1002, 1003) ORDER BY prod_name;
```
**IN** WHERE子句中用来指定要匹配值的清单的关键字，功能与OR相当。
使用IN的优点如下：
 * 在使用长的合法选项清单时，IN操作符的语法更清楚且更直观；
 * 在使用IN时，计算的次序更容易管理（因为使用的操作符更少）；
 * IN操作符一般比OR操作符清单执行更快；
 * IN的最大优点是可以包含其他SELECT语句，使得能够更动态地建立WHERE子句。
 
#### NOT操作符
WHERE子句中的NOT操作符有且只有一个功能，那就是否定它之后所跟的任何条件。


```
SELECT prod_name, prod_price FROM products WHERE vend_id NOT IN (1002, 1003) ORDER BY prod_name;
```
这里的NOT否定跟在它之后的条件，因此，MySQL不是匹配1002和1003 的vend_id ， 而是匹配1002 和1003 之外供应商的vend_id。

