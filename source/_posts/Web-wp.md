---
title: Web-wp
date: 2021-04-16 12:48:41
categories: "CTF"
tags: "CTF"
---
歪脖的达不溜屁
<!--more-->

# ctfshow

## web入门

### 信息搜集

#### web1

简单的f12

#### web2

打开页面提示无法查看源代码 迷惑.jpg

我一下就打开了，很快啊

看了下hint，get新知识，在URL头部添加`view-source:`即可查看源码

（原来是禁用了右键，习惯用快捷键真是不好意西:-)

#### web3

bp抓包，flag在返回包里

#### web4

打开robots.txt，得到一个flagishere.txt，打开`/flagishere.txt`，得到flag

#### web5

在URL尾部输入`/index.phps`，得到phps文件，打开得到flag

#### web6

提示应该是源码泄露，用dirsearch扫了一下发现`www.zip`，下载到本地得到一个fl000g.txt文件，打开得到个flag{flag_here}，提交错误

...原来是个假flag，在URL尾部输入`/fl000g.txt`得到真flag

#### web7

根据提示感觉应该是git泄露，URL尾部添加`/.git/`，得到flag

#### web8

git泄露都考了，应该就是svn了，URL尾部添加`/.svn/`，得到flag

# bugku

## web1
...滑稽脸
<img src="https://z3.ax1x.com/2021/04/16/cf8LQK.jpg" style="zoom: 25%;" />
F12打开源码，找到flag

## web2
是一个填写验证码的输入框，然后发现无法输入两个字符，F12审查元素，果然输入框限制了maxlength，修改maxlength为2即可

## web3
打开场景是一段PHP代码，
```php
$what=$_GET['what'];
echo $what;
if($what=='flag')
echo 'flag{****}';
```
审计，是要通过get的方式提交一个变量`what=flag`，
在地址栏输入`http://114.67.246.176:16477/?what=flag`即可得到flag

## web4
打开场景又是一段PHP代码，
```php
$what=$_POST['what'];
echo $what;
if($what=='flag')
echo 'flag{****}';
```
审计，是要通过post的方式提交一个变量`what=flag`,通过hackbar post一下即可

## web5
打开场景又是一段PHP代码，
```php
$num=$_GET['num'];
if(!is_numeric($num))
{
echo $num;
if($num==1)
echo 'flag{**********}';
}
```
审计，是弱类型比较，要求num变量既不是数字又满足等于1的条件，所以在1后面加一个字母即可
通过get方式提交`http://114.67.246.176:12222/?num=1a`
得到flag

## web6
打开场景一堆弹窗，关都关不完，查看网页源码，
![](https://z3.ax1x.com/2021/04/13/cyMAh9.png)
...发现写了一堆alert...绝了
在最下面发现了注释掉的编码，
![](https://z3.ax1x.com/2021/04/13/cyMunK.png)
查了一下是Unicode编码，通过工具Unicode转ASCII得到flag

## web7
弹窗提示停止网页刷新可得到flag
查看网页源代码，发现
![](https://z3.ax1x.com/2021/04/20/cH8KiT.jpg)
并且前面的图片命名为num.jpg，于是尝试刷新，发现图片num确实随着刷新改变，然后不断刷新，最后在一次刷新后圈圈的地方出现flag

## web8
> PHP暂略
## web9
> PHP暂略
## web 10
打开页面显示什么也没有？信个鬼
根据描述头等舱，联想到消息头，BP抓包，在消息头中得到flag

# ctfhub

## web前置技能

### HTTP协议

#### 请求方式

HTTP/1.1 八种请求方式: GET,POST,HEAD,OPTIONS,PUT,DELETE,TRACE,CONNECT

打开环境提示HTTP方法为GET，使用CTFHUB方法，我会给你flag

bp抓包改包重放，得到flag

