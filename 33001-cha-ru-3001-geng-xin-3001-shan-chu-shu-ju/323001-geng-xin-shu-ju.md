### 更新数据
为了更新（修改）表中的数据，可使用UPDATE语句。可采用两种方式使用UPDATE：
* 更新表中特定行；
* 更新表中所有行。
基本的UPDATE语句由3部分组成，分别是：
* 要更新的表；
* 列名和它们的新值；
* 确定要更新行的过滤条件。


```
UPDATE customers SET cust_email = 'elmer@fudd.com' WHERE cust_id = 10005;
```

在更新多个列时，只需要使用单个SET命令，每个“列=值”对之间用逗号分隔（最后一列之后不用逗号）。
### 删除数据
两种方式使用DELETE：
* 从表中删除特定的行；
* 从表中删除所有行。
从customers表中删除一行：


```
DELETE FORM customers WHERE cust_id = 10006;
```
**
如果执行UPDATE而不带WHERE子句，则表中每个行都将用新值更新。类似地，如果执行DELETE语句而不带WHERE子句，表的所有数据都将被删除。**

**使用UPDATE或DELETE时所遵循的习惯**：
* 除非确实打算更新和删除每一行，否则绝对不要使用不带WHERE子句的UPDATE或DELETE语句；
* 保证每个表都有主键，尽可能像WHERE子句那样使用它（可以指定各主键、多个值或值的范围）；
* 在对UPDATE或DELETE语句使用WHERE子句前，应该先用SELECT进行测试，保证它过滤的是正确的记录，以防编写的WHERE子句不正确；
* 使用强制实施引用完整性的数据库，这样MySQL将不允许删除具有与其他表相关联的数据的行。