---
title: CTF学习笔记
date: 2021-05-27 19:47:32
categories:	CTF
tags: CTF
---
萌新的入坑记录而已
<!--more-->
# SQL注入
## 登录界面
> 登录界面必然会与数据库进行交互，所以是SQL注入的经典位置

常见登陆界面SQL语句`select * from admin where username = '用户输入的用户名' and password = '用户输入的密码'`
万能用户名:`' or 1=1 -- ` 	(`-- `后面有一个空格)
第一个`'`用于闭合SQL语句用户名的单引号，`1=1`永远为真，`-- `用于注释其后的密码语句，从而绕过登录验证 
