# Ubuntu 操作

## Ubuntu防火墙

### 检查防火墙是否启动

```Ubuntu
 sudo ufw status verbose
 
 Status: inactive//未启用
 Status: active//启用
```

### 启用

```ubuntu
sudo ufw enable
sudo ufw default deny
```

### 开放端口

```ubuntu
sudo ufw allow 53 允许外部访问53端口(tcp/udp)

sudo ufw allow 3690 允许外部访问3690端口(svn)

sudo ufw allow from 192.168.1.111 允许此IP访问所有的本机端口

sudo ufw allow proto tcp from 192.168.0.0/24 to any port 22  允许指定的IP段访问特定端口

sudo ufw delete allow smtp 删除上面建立的某条规则，比如删除svn端口就是 sudo ufw delete allow 3690 
```

### 简单使用

```ubuntu
下面是ufw命令行的一些示例：

ufw enable/disable：打开/关闭ufw

ufw status：查看已经定义的ufw规则

ufw default allow/deny：外来访问默认允许/拒绝

ufw allow/deny 20：允许/拒绝访问20端口，20后可跟/tcp或/udp，表示tcp或udp封包。

sudo ufw allow proto tcp from 192.168.0.0/24 to any port 22：允许自192.168.0.0/24的tcp封包访问本机的22端口。

ufw delete allow/deny 20：删除以前定义的"允许/拒绝访问20端口"的规则
```

## Ubuntu文件权限

-rw------- (600) 只有所有者才有读和写的权限

-rw-r–r-- (644) 只有所有者才有读和写的权限，组群和其他人只有读的权限

-rwx------ (700) 只有所有者才有读，写，执行的权限

-rwxr-xr-x (755) 只有所有者才有读，写，执行的权限，组群和其他人只有读和执行的权限

-rwx–x--x (711) 只有所有者才有读，写，执行的权限，组群和其他人只有执行的权限

-rw-rw-rw- (666) 每个人都有读写的权限

-rwxrwxrwx (777) 每个人都有读写和执行的权限

==以上所有数字称之为== **权限编号** 

### 修改文件权限

```ubuntu
sudo chmod 权限编号 文件名

sudo chmod 600 ××× （只有所有者有读和写的权限）

sudo chmod 644 ××× （所有者有读和写的权限，组用户只有读的权限）

sudo chmod 700 ××× （只有所有者有读和写以及执行的权限）

sudo chmod 666 ××× （每个人都有读和写的权限）

sudo chmod 777 ××× （每个人都有读和写以及执行的权限）
```

## Ubuntu一系统设置(重装系统后)

root用户设置密码的具体步骤：打开一个terminal，然后输入下面的命令sudo passwd

### 终端中文化

#### 1.安装中文包 apt update

```ubuntu
apt update  
apt install language-pack-zh-hans
```

#### 2.将区域语言设置为简体中文

```ubuntu
localectl set-locale LANG=zh_CN.utf8
```

### 自动挂载数据盘

新建挂载点 mkdir <挂载点>

以新建挂载点 /data 为例：

mkdir /data

将新建分区挂载至新建的挂载点。

mount /dev/vdb <挂载点>

以新建挂载点 /data 为例：

mount /dev/vdb /data

查看挂载结果

df -TH

查看弹性云硬盘的软链接。

ls -l /dev/disk/by-id

备份 /etc/fstab 文件

cp -r /etc/fstab /home

使用 VI 编辑器打开 /etc/fstab 文件。

vi /etc/fstab

以使用弹性云硬盘的软链接自动挂载为例，结合前文示例则添加：

/dev/disk/by-id/virtio-disk-9601acej /data ext4 defaults 0 0

检查 /etc/fstab 文件是否写入成功。

mount -a 

更新源

sudo apt-get update 

更新软件

sudo apt-get upgrade

更新系统软件 

sudo apt-get dist-upgrade

### 安装apache

sudo apt install apache2 -y

### 安装Mysql - 先别接着修改root密码

sudo apt install mysql-server mysql-client

### 安装PHP

sudo apt-get install php

### 安装关联

sudo apt-get install libapache2-mod-php

sudo apt-get install php-mysql

### 进入mysql

sudo mysql # 回车后 输入系统用户密码

更改mysql默认root用户密码

ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY '新密码'; #更改mysql的默认root用户密码

FLUSH PRIVILEGES;

quit; # 退出mysql

sudo service mysql restart # 重启mysql

再次登录使用 ==mysql -uroot -p==回车后输入密码

### mysql远程访问

#### 1.**设置root账号为远程访问**

mysql> ALTER USER 'root'@'localhost' IDENTIFIED BY 'password' PASSWORD EXPIRE NEVER; #修改加密规则

mysql> ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY '新密码'; #使用mysql_native_password重新修改密码

mysql> UPDATE mysql.user SET host = '%' WHERE user = 'root'; #允许远程访问

mysql> FLUSH PRIVILEGES;

#### **2.新增用户赋权并设置远程访问**

mysql> CREATE USER 'sammy'@'%' IDENTIFIED WITH mysql_native_password BY 'password';

mysql> GRANT ALL PRIVILEGES ON *.* TO 'sammy'@'%' WITH GRANT OPTION;

### mysql 数据库路径修改

#### 1、先关闭mysql数据库服务
/etc/init.d/mysql stop

#### 2、创建新目录

mkdir /data/mysql

#### 3、复制数据到新目录

cp -R /var/lib/mysql/* /data/mysql

#### 4、修改data目录的权限

chown -R mysql:mysql  /data/mysql

#### 5、编辑mysql的配置文件

#将 [mysqld] 组下的 datadir改为：
注如前有#号一定删除

```mysql
vim /etc/mysql/mysql.conf.d/mysqld.cnf 


datadir=/data/mysql
```

#### 6、修改启动文件

```mysql
sudo vim /etc/apparmor.d/usr.sbin.mysqld
# Allow data dir access
  /var/lib/mysql/ r,
  /var/lib/mysql/** rwk,
  修改为
# Allow data dir access
  /data/mysql/ r,
  /data/mysql/** rwk,
```

#### 7、重启MySQL

sudo /etc/init.d/apparmor restart
sudo /etc/init.d/mysql restart

#### 8、登录MySql并验证数据目录

mysql -u root -p

show variables like '%dir%';
<==当显示datadir 为/data/mysql时，修改成功

