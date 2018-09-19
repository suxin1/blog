## MySql  使用技巧

##### 创建数据库时：

```sql
CREATE DATABASE `test`  
CHARACTER SET 'utf8'  
COLLATE 'utf8_general_ci';
```

#####创建数据表时：

```Sql
CREATE TABLE `database_user` (  
`ID` varchar(40) NOT NULL default '',  
`UserID` varchar(40) NOT NULL default '',  
) ENGINE=InnoDB DEFAULT CHARSET=utf8; 
```

##### 更改数据库编码：

```Sql
ALTER DATABASE `database` DEFAULT CHARACTER SET utf8 COLLATE utf8_general_ci;
```

##### 更改数据表编码：

```SQL
ALTER TABLE `table` DEFAULT CHARACTER SET utf8 COLLATE utf8_general_ci; 
```

##### 查看默认编码格式：

```Sql
show variables like "%char%"; 
```

#### Python Sqlalchemy 链接到数据库：        

```
mysql://root:123456@localhost:3306/shop_dev?charset=utf8n
```

#### 重置密码

本篇只列举在OSX系统下的操作

1. 关闭Preferences 中关闭mysql server，或执行：

   ```bash
   sudo /usr/local/mysql/support-files/mysql.server stop
   ```

2. 重启mysql server with —skip-grant-tables

   ```bash
   sudo mysqld_safe --skip-grant-tables
   ```

3. 链接到mysql server，这时候不需要密码。现在就可以执行下面的命令重置密码了：

   ```sql
   mysql> FLUSH PRIVILEGES;
   mysql> ALTER USER 'root'@'localhost' IDENTIFIED BY 'MyNewPass';
   ```

   ​

   ​