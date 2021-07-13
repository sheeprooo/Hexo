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
<img src="https://z3.ax1x.com/2021/04/13/cyMAh9.png" style="zoom:33%;" />
...发现写了一堆alert...绝了
在最下面发现了注释掉的编码，
<img src="https://z3.ax1x.com/2021/04/13/cyMunK.png" style="zoom: 33%;" />
查了一下是Unicode编码，通过工具Unicode转ASCII得到flag

## web7
弹窗提示停止网页刷新可得到flag
查看网页源代码，发现
<img src="https://z3.ax1x.com/2021/04/20/cH8KiT.jpg" style="zoom: 50%;" />
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

#### 302跳转

看了wp才做出来

打开环境，点击got flag后没反应，f12查看新出现了一个302的index.php页面，使用curl工具`-v`参数输出通信的整个过程，得到flag

#### cookie

打开环境提示管理员才能得到flag

使用EditThisCookie查看，有一个名为admin的cookie值为0，修改为1，刷新得到flag

#### 基础认证

打开环境，有个获得flag的click按钮，点一下弹出窗口需要登陆验证，随便输一个`admin/123`，bp抓包

<img src="web-wp/1.jpg" style="zoom:33%;" />

头部有一个Authorization字段，后面的值解码发现是base64加密的`admin:123`

<img src="web-wp/2.jpg" style="zoom:33%;" />

在返回包里发现提示

<img src="web-wp/3.jpg" style="zoom:33%;" />

猜测用户名为admin

下面就可以尝试爆破了，发送到Intruder模块，添加payload position

<img src="web-wp/4.jpg" style="zoom:33%;" />

选择模式，加载字典

<img src="web-wp/5.jpg" style="zoom: 33%;" />

添加前缀`admin:`，并对密码进行base64加密处理（同时取消勾选URL编码，不然你会看到 base64 之后的 `=` 会被转成 `%3d` ，你就算爆破到天荒地老也不会出来）

<img src="web-wp/6.jpg" style="zoom:33%;" />

最后在一个状态码为200的响应返回包中发现flag

#### 响应包源代码

饿饿. 打开环境查看源码 发现flag...我人傻了
