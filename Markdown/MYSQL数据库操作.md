# Mysql数据库操作

------



## 登陆mysql

```mysql
mysql -uroot -p  
```

==登陆密码wangqianlong0==

### 增加新用户

```mysql
grant 权限 on 数据库.\* to 用户名@登录主机 identified by "密码"
```
增加一个用户user密码为password，让其可以在本机上登录， 并对所有数据库有查询、插入、修改、删除的权限。首先用以root用户连入mysql，然后键入以下命令：
```mysql
grant select,insert,update,delete on . to user@localhost Identified by “password”;
```
如果希望该用户能够在任何机器上登陆mysql，则将localhost改为”%”.

### 启动(采用service方式)

```mysql
service mysql start 
```

停止mysql服务只需要将start改为stop即可; 重启将start改为restart

### 查看mysql是否在监听端口命令

```mysql
$netstat -tl | grep mysql
```



------



## 操作数据库

登录到mysql中，然后在mysql的提示符下运行下列命令，每个命令以分号结束。
### 使用数据库

```mysql
use 数据库名;
```

###  建库与删库

```mysql
create database 库名;
drop database 库名;
```

### 建表与删表

```mysql
use 库名;
create table 表名(字段列表);
drop table 表名;
```

### 清空表中记录

```mysql
delete from 表名;
```

### 显示表中的记录

```mysql
select * from 表名;
```

### 查看所有数据库

```mysql
show databases;
```

###  显示mysql库中的数据表

```mysql
use mysql;
show tables;
```

### 显示数据表的结构

```mysql
describe 表名;
```

### 显示表格列的属性

```mysql
show columns from tableName；
```



### 数据类型介绍

|  数字类型  |                                           |           字符串类型           |                                      |
| :--------: | :---------------------------------------: | :----------------------------: | :----------------------------------: |
|    整数    | tinyint、smallint、mediumint、int、bigint |             字符串             |            char、varchar             |
|   浮点数   |       float、double、real、decimal        |              文本              | tinytext、text、mediumtext、longtext |
| 日期和时间 |   date、time、datetime、timestamp、year   | 二进制(可用来存储图片、音乐等) | tinyblob、blob、mediumblob、longblob |

### 创建索引

```mysql
alter table table1 add index ind_id (id);
create index ind_id on table1 (id);
create unique index ind_id on table1 (id);//建立唯一性索引
　　
```

### 删除索引

```mysql
drop index idx_id on table1;
alter table table1 drop index ind_id;
```

