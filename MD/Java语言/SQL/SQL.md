# SQL-1999

-----------------

## 什么是SQL

* sql概念：*结构化查询语言*(Structured Query Language)简称‘SQL‘
* sql分类：
  * DML:数据操作语言(CRUD)
  * DDL:数据定义语言

# SQL常见语法

* 基本操作

  | 编号 |   功能   |                         语句                         |
  | :--: | :------: | :--------------------------------------------------: |
  |  1   |  insert  |   insert into tableName values (att1,att2,att3..)    |
  |  2   |  delete  |                delete from tableName                 |
  |  3   |  update  |           update tableName set att = value           |
  |  4   |  select  |          select att1,att2,.. from tableName          |
  |  5   | distinct |         select distinct att1 from tableName          |
  |  6   | order by | select * from tableName order by att1 asc ,att2 desc |
  |      |          |                                                      |

* 查询进阶

  * 子查询

    1. select子查询

       * 将查询出来的结果作为查询条件再次进行查询

         ```sql
         select (select att1 from table1) from table2;
         ```

    2. from子查询

       * 将查询出来的结果作为数据进行二次查询

         ```sql
         select * from (select * from table1 where att1 = value1 );
         ```

    3. where子查询

       * 查询出来的结果作为查询条件再次进行查询

         ```sql
         select * from table1 where att1 = (select distinct att1 from table2 where att2 = value2) and att2 in (select att1 from table3)
         ```

  * 关联查询

    1. 内连接

       ```sql
       select t1.att1 , t2.att1 from table1 t1 inner join table2 t2 where t1.att2 = t2.att2 
       ```

    2. 外连接查询

       ```sql
       
       select t1.att1 , t2.att1 from table1 t1 left join table2 t2 on t1.att2 = t2.att2 ;
       
       select t1.att1 , t2.att1 from table1 t1 right join table2 t2 on t1.att2 = t2.att2 ;
       ```

    3. 交叉连接

       ```sql
       select t1.att1 , t2.att1 from table1 t1 cross join table2 t2 where t1.att2 = t2.att2 
       ```












    ​		

