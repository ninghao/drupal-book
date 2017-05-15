# 安装 Drupal

生成随机密码：

```
openssl rand -base64 32
```

返回类似：

```
rDhVQ2kvu9K3tVZ7IGqJ42cdNmh0o3jqKLndyzBoOs4=
```

登录 MySQL 命令行，或者使用 phpMyAdmin 创建数据库。

```
mysql -u root -p
```

输入 root 用户的密码登录到 MySQL。

创建数据库

```
create database drupal;
```

返回：

```
Query OK, 1 row affected (0.01 sec)
```

查看数据库

```
show databases;
```

显示

```
+--------------------+
| Database           |
+--------------------+
| drupal             |
| information_schema |
| mysql              |
| performance_schema |
+--------------------+
4 rows in set (0.01 sec)
```

设置数据库用户

```
grant all privileges on drupal.* to 'drupal'@'localhost' identified by 'rDhVQ2kvu9K3tVZ7IGqJ42cdNmh0o3jqKLndyzBoOs4=';
```

返回

```
Query OK, 0 rows affected (0.06 sec)
```



