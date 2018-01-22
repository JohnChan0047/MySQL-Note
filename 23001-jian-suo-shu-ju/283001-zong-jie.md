### 子查询
**查询（query）** 任何SQL语句都是查询。但此术语一般指SELECT语句。
SQL还允许创建子查询（subquery），即嵌套在其他查询中的查询。


```
SELECT cust_name, cust_contact FROM customers WHERE cust_id IN (SELECT cust_id FROM orders WHERE orders WHERE order_num IN (SELECT order_num FROM orderitems WHERE prod_id = 'TNT2'))
```

