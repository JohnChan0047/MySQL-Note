**字段（field）** 基本上与列（column）的意思相同，经常互换使用，不过数据库列一般称为列，而术语字段通常用在计算字段的连接上。
### 拼接字段


```
SELECT Concat(vend_name, '(', vend_country, ')') FROM vendors ORDER BY vend_name;
```

输出结果：![](/assets/拼接.png)

**Concat()**拼接串，即把多个串连接起来形成一个较长的串。Concat()需要一个或多个指定的串，各个串之间用逗号分隔。


```
SELECT Concat(RTrim(vend_name), '(', RTrim(vend_country), ')') FROM vendors ORDER BY vend_name;
```

**RTrim()**函数去掉值右边的所有空格。通过使用RTrim()，各个列都进行了整理。
**Trim函数** MySQL除了支持RTrim()（正如刚才所见，它去掉串右边的空格），还支持LTrim()（去掉串左边的空格）以及Trim()（去掉串左右两边的空格）。

### 使用别名


```
SELECT Concat(RTrim(vend_name), '(', RTrim(vend_country), ')') AS vend_title FROM vendors ORDER BY vend_name;
```

输出![](/assets/别名.png)
### 执行算术计算


```
SELECT prod_id， quantity, item_price, quantity*item_price AS expanded_price FROM orderitems WHERE  order_num = 2005;
```
输出![](/assets/别名计算.png)

