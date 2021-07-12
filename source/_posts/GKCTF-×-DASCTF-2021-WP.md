---
title: GKCTF × DASCTF 2021 WP
date: 2021-06-26 17:43:59
tags:	CTF
categories:	CTF
---

只有一道题

<!--more-->

# easycms

打开是一个CMS做的企业用户网站，翻到最下面找到CMS类型

![](GKCTF-×-DASCTF-2021-WP/1.jpg)

百度此类型CMS漏洞或后台等信息，在官网搜到

![](GKCTF-×-DASCTF-2021-WP/2.jpg)

打开`http://xxx.node3.buuoj.cn/admin.php`

<img src="GKCTF-×-DASCTF-2021-WP/3.jpg" style="zoom:33%;" />

根据提示密码是五位弱口令，而Email还可以是用户名

正好主页

<img src="GKCTF-×-DASCTF-2021-WP/4.jpg" style="zoom: 50%;" />

于是我就输入了这个邮箱，尝试11111，12345等最常见的五位弱口令，不对！...

后来经过出题人的提示才知道用户名不需要信息收集...

最后以admin/12345成功登录

登录后台后，查资料得到蝉知后台getshell的方法

[禅知后台getshell - Wiki](https://wiki.96.mk/Web安全/禅知/禅知后台getshell/)

进行测试发现由于版本不同，此版本已无法进行复现此漏洞

在后台模板尝试修改

<img src="GKCTF-×-DASCTF-2021-WP/5.jpg" style="zoom: 25%;" />

为了创建文件找到可以上传文件的地方

<img src="GKCTF-×-DASCTF-2021-WP/6.jpg" style="zoom: 25%;" />

随便上传一个txt文件，修改文件名

然后再编辑模板即可保存

编辑后返回前台得到flag

<img src="GKCTF-×-DASCTF-2021-WP/7.jpg" style="zoom: 25%;" />

