# mysql

## desc

```sql
1、desc 可用于降序排序
desc用于降序作用时表示的是【descend v.下降】 的缩写。

select *
from product
order by price; -- 默认升序

select *
from product
order by price desc; -- desc 降序

// 注：product 是表名，price 是属性



2、desc 查看表信息
desc 用于查看表信息时表示的是【 describe v.描述】的缩写。

desc product; -- 查看表信息
// 注：product 是表名

```

## 比较

![mysql1](.\mysql1.png)

### 非符号运算符

![mysql2](.\mysql2.png)

## 顺序

```java
#原因是执行顺序，先FROM 然后WHERE 然后SELECT...的原因
```

## 连接

![mysql3](.\mysql3.png)

## 索引

### 普通索引

#### 创建索引

```sql
CREATE INDEX indexName ON table_name (column_name)
```

#### 修改表结构添加索引

```sql
ALTER table tableName ADD INDEX indexName(columnName)
```

#### 创建表时直接指定

```sql
CREATE TABLE mytable(  
 
ID INT NOT NULL,   
 
username VARCHAR(16) NOT NULL,  
 
INDEX [indexName] (username(length))  
 
);  
```

#### 删除索引

```sql
DROP INDEX [indexName] ON mytable; 
```



## 从数据库中随机取50条数据

```sql
select * from 表 order by rand() limit50;
```



## 数据库操作

### 创建

```sql
CREATE TABLE IF NOT EXISTS `runoob_tbl`(
   `runoob_id` INT UNSIGNED AUTO_INCREMENT,
   `runoob_title` VARCHAR(100) NOT NULL,
   `runoob_author` VARCHAR(40) NOT NULL,
   `submission_date` DATE,
   PRIMARY KEY ( `runoob_id` )
)ENGINE=InnoDB DEFAULT CHARSET=utf8;
```



### 修改

新增

```sql
alter table om_port_employee_t add EMP_SNO VARCHAR2(50);
```

删除

```sql
alter table om_port_employee_t drop column EMP_Description;
```

改名

```sql
alter table om_port_employee_t rename to employee;
```



## 分析sql执行慢的原因

https://blog.csdn.net/warybee/article/details/122637466?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522166839085716800182757208%2522%252C%2522scm%2522%253A%252220140713.130102334.pc%255Fall.%2522%257D&request_id=166839085716800182757208&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~first_rank_ecpm_v1~rank_v31_ecpm-1-122637466-null-null.142^v63^control,201^v3^control_1,213^v2^t3_control2&utm_term=%E5%88%86%E6%9E%90%20SQL%20%E6%89%A7%E8%A1%8C%E5%8F%A5%E8%AF%9D%EF%BC%8C%E6%98%AF%E5%90%A6%E5%91%BD%E4%B8%AD%E7%B4%A2%E5%BC%95%E7%AD%89&spm=1018.2226.3001.4187





1. 通过慢查询日志定位执行慢的 SQL；
2. 使用 `EXPLAIN` 分析该 SQL 语句是否使用到了索引，以及具体的数据表访问方式；
3. 使用`SHOW PROFILE` 进一步分析SQL的每一步执行时间以及CPU、IO等资源使用情况。

### 1.通过慢查询日志定位执行慢的 SQL；

  慢查询日志是MySQL提供的一种日志记录，它用来记录所有执行时间超过`long_query_time`参数值的SQL。`long_query_time`的默认值为10秒，默认情况下执行超过10s的SQL语句，会被记录到慢查询日志中。

#### 查看是否开启

```sql
show variables like '%slow_query_log%';
```

#### 开启

```sql
set global slow_query_log='ON';
```

`slow_query_log_file` 是慢查询日志文件目录。

#### 设置慢查询时间阈值

```sql
set global long_query_time = 1;
```









## 面试

https://blog.csdn.net/weixin_45366499/article/details/119515015?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522166839052216800192220798%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=166839052216800192220798&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~top_positive~default-2-119515015-null-null.142^v63^control,201^v3^control_1,213^v2^t3_control2&utm_term=mysql%E9%9D%A2%E8%AF%95&spm=1018.2226.3001.4187

https://mp.weixin.qq.com/s/MJuDPMUirIbjm6XTuVUAyw
https://www.jianshu.com/p/3a732d30102d
https://mp.weixin.qq.com/s/8ddEzG-NzzFD35ehvbER7A
https://mp.weixin.qq.com/s/vdOOVQtZhrJXsvRUjq0HqQ

