## 按一个列排序数据
```
SELECT prod_name FROM products ORDER BY prod_name;
```

## 按多个列排序数据
```
SELECT prod_id, prod_price, prod_name FROM products ORDER BY prod_price, prod_name;
```
对于上述例子中的输出，仅在多个行具有相同的prod_price值时才对产品按prod_name进行排序。如果prod_price列中所有的值都是唯一的，则不会按prod_name排序。
## 指定排序方向
```
SELECT prod_id, prod_price, prod_name FROM products ORDER BY prod_price DESC;
```
DESC关键字只应用到直接位于其前面的列名。

**在多个列上降序排序** 如果想在多个列上进行降序排序，必须对每个列指定DESC关键字。