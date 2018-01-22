### 创建组合查询
可用UNION操作符来组合数条SQL查询。利用UNION，可给出多条SELECT语句，将它们的结果组合成单个结果集。
UNION的使用很简单。所需做的只是给出每条SELECT语句，在各条语句之间放上关键字UNION。


```
SELECT vend_id, prod_id, prod_price FROM products WHERE prod_price <= 5
UNION
SELECT vend_id, prod_id, prod_price FROM products WHERE vend_id IN (1001, 1002);
```
**UNION规则**
* UNION必须由两条或两条以上的SELECT语句组成，语句之间用关键字UNION分隔（因此，如果组合4条SELECT语句，将要使用3个UNION关键字）;
* UNION中的每个查询必须包含相同的列、表达式或聚集函数（不过各个列不需要以相同的次序列出）;
* 列数据类型必须兼容：类型不必完全相同，但必须是DBMS可以隐含地转换的类型（例如，不同的数值类型或不同的日期类型）。
UNION默认消除重复的行，可使用UNION ALL 返回全部行。