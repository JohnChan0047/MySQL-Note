### 常见的文本处理函数
![](/assets/文本处理函数.png)
![](/assets/文本处理函数2.png)
### 常用日期和时间处理函数
![](/assets/时间处理.png)


```
SELECT cust_id, order_num FROM orders WHERE Date(order_date) BETWEEN '2005-09-01' AND '2005-09-30'；
SELECT cust_id, order_num FROM orders WHERE Year(order_date) = 2005 AND Month(order_date) = 9;
```

### 数值处理函数
![](/assets/常用数值处理函数.png)
### 聚集函数（aggregate function）运行在行组上，计算和返回单个值的函数
![](/assets/聚集函数.png)


```
SELECT COUNT(*) AS num_items, MIN(prod_price) AS price_min, MAX(prod_price) AS price_max, AVG(prod_price) AS price_avg FROM products;
```

![](/assets/聚集计算例子.png)
### 分组数据


```
SELECT vend_id, COUNT(*) AS num_prods FROM products GROUP BY vend_id;
```

![](/assets/group.png)

### 过滤分组


```
SELECT cust_id, COUNT(*) AS orders FROM orders GROUP BY cust_id HAVING COUNT(*) >= 2;
```
它列出具有2个（含）以上、价格为10（含）以上的产品的供应商：


```
SELECT vend_id, COUNT(*) AS num_prods FROM products WHERE prod_price >= 10 GROUP BY vend_id HAVING COUNT(*) >= 2;
```
### 分组和排序

![](/assets/分组和排序.png)
