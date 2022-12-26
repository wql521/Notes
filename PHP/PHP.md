# PHP

## PHP 页面

### php定时跳转页面

```php
header("refresh:3;url=http://www.wangqianlong.com/pages/3d/xinxin.html");
```

三秒后跳转xinxin.html页面

## php数据库操作

### php连接mysql数据库

```php
<?php
$host='localhost';  // 数据库主机名
$username="root";   // 数据库用户名
$password="wangqianlong0";  // 数据库密码
$dbname="Users";    // 数据库名
$connID=mysqli_connect($host,$username,$password,$dbname);  // 建立数据库连接
if (mysqli_select_db($connID,$dbname)) {    // 选择数据库
    echo "数据库连接成功"; // 数据库连接成功
}
else  
{
    echo "数据库连接失败"; // 数据库连接失败
}
?>
```

### php 创建操作数据库方法的类

```php
<?php

class Mysql_DB
{
// 定义属性
    public string $host='localhost';  // 数据库主机名
    public string $user='root';  // 数据库用户名
    public string $password='wangqianlong0';  // 数据库密码
    public string $dbname='Users';    // 数据库名

// 增加数据
public function add($connID,$table,$data)
{
    $keys=join(",",array_keys($data));  // 获取数组的键名
    $vals="'".join("','",array_values($data))."'";  // 获取数组的键值
    $sql="insert into {$table}({$keys}) values({$vals})";   // 创建sql语句
    mysqli_query($connID,$sql); // 执行sql语句
}
// 删除数据
public function delete($connID,$table,$where)
{
    $where="delete from {$table} where {$where}";   // 创建sql语句
    mysqli_query($connID,$where);   // 执行sql语句
}
// 更新数据
public function update($connID,$table,$data,$where)
{
    foreach ($data as $key => $val) {   // 遍历数组
        $val="'$val'";  // 将键值转换为字符串
        $keyArr[]="{$key}={$val}";  // 将键值放入数组
    }
    $keystr=join(",",$keyArr);  // 将数组转换为字符串
    $where="update {$table} set {$keystr} where {$where}";  // 创建sql语句
    mysqli_query($connID,$where);   // 执行sql语句
}
// 查询数据
public function select($connID,$table,$where)
{
    $where="select * from {$table} where {$where}"; // 创建sql语句
    $result=mysqli_query($connID,$where);   // 执行sql语句
    while ($row=mysqli_fetch_assoc($result)) {  // 将查询结果转换为数组
        $rows[]=$row;   // 将数组放入数组
    }
    return $rows;   // 返回数组
}
// 查询数据总数
public function selectAll($connID,$table)
{
    $sql="select * from {$table}";  // 创建sql语句
    $result=mysqli_query($connID,$sql);  // 执行sql语句
    $num=mysqli_num_rows($result);  // 获取查询结果的行数
    return $num;    // 返回行数
}
// 查询数据总数
public function selectPage($connID,$table,$page,$pagesize)
{
    $sql="select * from {$table} limit {$page},{$pagesize}";    // 创建sql语句
    $result=mysqli_query($connID,$sql); // 执行sql语句
    while ($row=mysqli_fetch_assoc($result)) {  // 将查询结果转换为数组
        $rows[]=$row;   // 将数组放入数组
    }
    return $rows;   // 返回数组
}
// 关闭数据库连接
public function close($connID): void
{
    mysqli_close($connID);  // 关闭数据库连接
}

    public function connect(): bool|mysqli
    {
        // 连接数据库
        return mysqli_connect($this->host,$this->user,$this->password,$this->dbname); // 返回连接标识符
    }
}
```

#### 数据库添加

```php
<?php
// 加载类
require 'Mysql_DB.php';
// 实例化对象
$db=new Mysql_DB();
// 连接数据库
$connID=$db->connect();
// 增加数据
// add($connID,$table,$data)
$db->add($connID,'users',['id'=>'2','name'=>'hx','password'=>'521']);
$db->close($connID);

```

> ==**$table**对应数据库中的数据表==
>
> ==**$data**为一个数组==  

##### 数组

php数组将values映射到keys的类型(PHP中数组的key可以是字符串，而values可以是任意类型)

```php
<?php
array("boo"=>true,1=>13,12=>"PHP","fl"=>6.46); // array()为创建数组的函数
?>
```

==**=>**连接键值对==

#### 数据删除

```php
<?php
// 加载类
require 'Mysql_DB.php';
// 实例化对象
$db=new Mysql_DB();
// 连接数据库
$connID=$db->connect();
// 删除数据
// delete($connID,$table,$where)
$db->delete($connID,'users','id=2');
// 关闭数据库连接
$db->close($connID);
```

> ==**$where**这里采用了主键id来寻找,具体逻辑有待进一步探究   **?**==

#### 数据查询

##### mysqli_query查询

```php
$sql_select = "SELECT * FROM users WHERE  IP='$ID'"; // 查询语句
$result = mysqli_query($connID,$sql_select); // 执行查询语句
$row = mysqli_fetch_array($result); // 获取查询结果
```

##### 函数查询

```php
public function select($connID,$table,$where)
{
    $where="select * from {$table} where {$where}"; // 创建sql语句
    $result=mysqli_query($connID,$where);   // 执行sql语句
    while ($row=mysqli_fetch_assoc($result)) {  // 将查询结果转换为数组
        $rows[]=$row;   // 将数组放入数组
    }
    return $rows;   // 返回数组
}
```

两者本质相同,仅仅调用不同
