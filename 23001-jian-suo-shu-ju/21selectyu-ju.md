## 检索单个列
```
SELECT prod_name FROM products;
```
上述语句利用SELECT 语句从products 表中检索一个名为prod_name的列。所需的列名在SELECT关键字之后给出，FROM关键字指出从其中检索数据的表名。

## 检索多个列
```
SELECT prod_id, prod_name, prod_price FROM products;
```

## 检索所有列
```
SELECT * FROM products;
```
如果给定一个通配符（`*`）,则返回表中所有列。

**使用通配符** 一般，除非你确实需要表中的每个列，否则最好别使用`*`通配符。虽然使用通配符可能会使你自己省事，不用明确列出所需列，但检索不需要的列通常会降低检索和应用程序的性能。

## 检索不同的行
```
SELECT DISTINCT vend_id FROM products; 
```
`SELECT DISTINCT vend_id`告诉MySQL只返回不同（唯一）的`vend_id`行,如果使用DISTINCT关键字，它必须直接放在列名的前面。

## 限制结果
```
SELECT prod_name FROM products LIMIT 5; 
```
LIMIT 5指示MySQL返回不多于5行。


```
SELECT prod_name FROM products LIMIT 5, 5; 
```
LIMIT 5, 5指示MySQL返回从行5开始的5行。第一个数为开始位置，第二个数为要检索的行数。。`LIMIT 4 OFFSET 3`意为从行3开始取4行，就像LIMIT 3, 4一样
