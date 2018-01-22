### 连结表
通过两个表的**主键**互为另一个表的**外键**，把2个表关联起来。

### 内部联结（等值联结）
```
SELECT vend_name, prod_name, prod_price FROM vendors, products WHERE vendors.vend_id = products.vend_id ORDER BY vend_name, prod_name;
```

### 自联结
### 自然联结
### 外部联结