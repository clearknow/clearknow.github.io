---
layout: post
title:  "绿色安装MySQL"
date:   2020-05-30 15:00:05
categories: python
tags: MySQL 安装
---


* content
{:toc}

>之前每次安装MySQL，都一直找一直找，哎搬运工太多了，又或者是大家环境都不一样吧







## 下载 MySQL5.8

*过程
	
	*网站：https://dev.mysql.com/
	*配置路径环境
	*重置密码：
		1.关闭MySQL
		2.打开dos（git也可以） 输入：mysqld --skip-grant-tables，别关掉
		3.再打开一个dos，成功进入（无需密码）
		4.重置密码，
			use mysql;
			delete from user where user='root';
			mysql> CREATE USER 'root'@'localhost' IDENTIFIED BY '123456';  （注1）
			mysql> GRANT ALL PRIVILEGES ON *.* TO 'root'@'localhost' WITH GRANT OPTION;
			mysql> CREATE USER 'root'@'%' IDENTIFIED BY '123456';
			mysql> GRANT ALL PRIVILEGES ON *.* TO 'root'@'%' WITH GRANT OPTION;
			注1：
			会提示：ERROR 1290 (HY000): The MySQL server is running with the --skip-grant-tables option so it cannot exe
			解决办法，在命令行输入：mysql> flush privileges;
	*搞定
















