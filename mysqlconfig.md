# Django 1.11.18 连接mysql数据库

## 1. 安装mysql数据库(安装至少两小时，网速太慢，都要放弃了)
```
# 卸载 mariadb rpm -e mariadb*
# 获取mysql安装包文件 wget http://repo.mysql.com/mysql-community-release-el7-5.noarch.rpm
# 安装 rpm -ivh mysql-community-release-el7-5.noarch.rpm 会生成两个yum源
# yum install mysql-server
# [root@localhost ~]# rpm -qa|grep mysql
# mysql57-community-release-el7-10.noarch
# mysql-community-client-5.7.28-1.el7.x86_64
# mysql-community-libs-5.7.28-1.el7.x86_64
# mysql-community-common-5.7.28-1.el7.x86_64
# mysql-community-server-5.7.28-1.el7.x86_64
```
## 2.创建用户远程连接mysql
```
# mysql -u root
# mysql > use
# mysql;
# mysql > update user set password = PASSWORD("这里输入root用户密码") where User = 'root';
# mysql > flush privileges;
# 问题1：ERROR 3009 (HY000): Column count of mysql.user is wrong. Expected 45, found 42. Created with MySQL 50564, now running 50728. Please use mysql_upgrade to fix this error.
# 解决1： mysql_upgrade -u root -p
# 创建用户
# mysql> insert into mysql.user(Host,User,Password,ssl_cipher,x509_issuer,x509_subject,
#      >authentication_string) values('localhost','mydj',password('mydj'), '','','','');
# or create user mydj identified by 'mydj';
# mysql> flush privileges;
# mysql> create database mydj
# mysql> grant all privileges on mydj.* to 'mydj'@'%' identified by 'mydj';
# mysql> flush privileges;

# 创建表
# mysql> create table class(
#     -> id INT NOT NULL AUTO_INCREMENT,
#     -> name VARCHAR(10) NOT NULL,
#     -> teacher VARCHAR(20) NOT NULL,
#     -> count INT,
#     -> create_date DATE,
#     -> PRIMARY KEY (id)
#     -> )ENGINE=InnoDB DEFAULT CHARSET=utf8;
# mysql> insert into class(id, name, teacher, count, create_date) values(1, 'law_one', 'jack', 30, '2019-11-20');
```
## 3. 配置mysql
```
# vim /etc/my.cnf
# [mysql]
# default-character-set=utf8
#
# [mysqld]
# character-set-server=utf8
# bind-address = 0.0.0.0
```
## 报错解决
```
# 关闭防火墙 systemctl stop firewalld

# python3 安装 mysql驱动
# pip install PyMySQL
# Django 配置文件
# 数据库相关配置
# DATABASES = {
#     'default': {
#         'ENGINE': 'django.db.backends.mysql',  #
#         'NAME': 'mydj',  # 数据库名称
#         'USER': 'mydj',  # 用户名
#         'PASSWORD': 'mydj',  # 密码
#         'HOST': '192.168.72.132',
#         'PORT': '3306',
#     }
#
# }
# Django连接mysql默认使用的是mysqldb驱动，所以需用改动
# lib/python3.6/site-packages/django/db/backends/mysql/__init__.py
# import pymysql
# pymysql.install_as_MySQLdb()
```
