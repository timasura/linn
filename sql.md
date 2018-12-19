### General

* 通用不等于SQL： select * from user where name <> 'alde' or name is null;


### Oracle

* 查询表注释： select * from user_tab_comments where table_name like 'PTP%';

* 查询字段注释： 
```sql

select 
  ut.table_name,--表名
  ut.column_name,--字段名称
  uc.comments,--字段注释
  ut.DATA_TYPE,--字典类型
  ut.DATA_LENGTH,--字典长度
  ut.NULLABLE--是否为空
from user_tab_columns  ut
inner join user_col_comments uc
on ut.table_name  = uc.table_name and ut.column_name = uc.column_name
where ut.table_name='MIC_DUN_INFO'
order by ut.column_name;

```


### Mysql

* 查询表注释： 

* 查询字段注释： 
