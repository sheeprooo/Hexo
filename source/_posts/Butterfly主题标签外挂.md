---
title: Tag Plugins
date: 2021-08-15 17:23:48
tags: 博客搭建
categories: 学习
description: Butterfly主题的标签外挂
sticky:
keywords:
  - HEXO
  - 博客
cover:
copyright: 
copyright_author: Jerry
copyright_author_href: 
copyright_url: https://butterfly.js.org/posts/dc584b87/
copyright_info: 本篇文章内容转载自Butterfly官方文档，如需转载/引用请访问原文链接
---

> 标签外挂是Hexo独有的功能，并不是标准的Markdown格式
>
> 以下的写法，只适用于Butterfly主题，用在其它主题上不会有效果，甚至可能会报错，使用前请留意

# Note (Bootstrap Callout)

## 用法一

```markdown
{% note [class] [no-icon] [style] %}
Any content (support inline tags too.io).
{% endnote %}
```

| 名称    | 用法                                                         |
| ------- | ------------------------------------------------------------ |
| class   | 【可选】标识，不同的标识有不同的配色<br>（ default / primary / success / info / warning / danger ） |
| no-icon | 【可选】不显示 icon                                          |
| style   | 【可选】可以覆盖配置中的 style<br/>（simple/modern/flat/disabled） |

### simple

```markdown
{% note simple %}
默认 提示块标籤
{% endnote %}

{% note default simple %}
default 提示块标籤
{% endnote %}

{% note primary simple %}
primary 提示块标籤
{% endnote %}

{% note success simple %}
success 提示块标籤
{% endnote %}

{% note info simple %}
info 提示块标籤
{% endnote %}

{% note warning simple %}
warning 提示块标籤
{% endnote %}

{% note danger simple %}
danger 提示块标籤
{% endnote %}
```

{% note simple %}
默认 提示块标籤
{% endnote %}

{% note default simple %}
default 提示块标籤
{% endnote %}

{% note primary simple %}
primary 提示块标籤
{% endnote %}

{% note success simple %}
success 提示块标籤
{% endnote %}

{% note info simple %}
info 提示块标籤
{% endnote %}

{% note warning simple %}
warning 提示块标籤
{% endnote %}

{% note danger simple %}
danger 提示块标籤
{% endnote %}

### modern

```markdown
{% note modern %}
默认 提示块标籤
{% endnote %}

{% note default modern %}
default 提示块标籤
{% endnote %}

{% note primary modern %}
primary 提示块标籤
{% endnote %}

{% note success modern %}
success 提示块标籤
{% endnote %}

{% note info modern %}
info 提示块标籤
{% endnote %}

{% note warning modern %}
warning 提示块标籤
{% endnote %}

{% note danger modern %}
danger 提示块标籤
{% endnote %}
```

{% note modern %}
默认 提示块标籤
{% endnote %}

{% note default modern %}
default 提示块标籤
{% endnote %}

{% note primary modern %}
primary 提示块标籤
{% endnote %}

{% note success modern %}
success 提示块标籤
{% endnote %}

{% note info modern %}
info 提示块标籤
{% endnote %}

{% note warning modern %}
warning 提示块标籤
{% endnote %}

{% note danger modern %}
danger 提示块标籤
{% endnote %}

### flat

```markdown
{% note flat %}
默认 提示块标籤
{% endnote %}

{% note default flat %}
default 提示块标籤
{% endnote %}

{% note primary flat %}
primary 提示块标籤
{% endnote %}

{% note success flat %}
success 提示块标籤
{% endnote %}

{% note info flat %}
info 提示块标籤
{% endnote %}

{% note warning flat %}
warning 提示块标籤
{% endnote %}

{% note danger flat %}
danger 提示块标籤
{% endnote %}
```

{% note flat %}
默认 提示块标籤
{% endnote %}

{% note default flat %}
default 提示块标籤
{% endnote %}

{% note primary flat %}
primary 提示块标籤
{% endnote %}

{% note success flat %}
success 提示块标籤
{% endnote %}

{% note info flat %}
info 提示块标籤
{% endnote %}

{% note warning flat %}
warning 提示块标籤
{% endnote %}

{% note danger flat %}
danger 提示块标籤
{% endnote %}

### disabled

```markdown
{% note disabled %}
默认 提示块标籤
{% endnote %}

{% note default disabled %}
default 提示块标籤
{% endnote %}

{% note primary disabled %}
primary 提示块标籤
{% endnote %}

{% note success disabled %}
success 提示块标籤
{% endnote %}

{% note info disabled %}
info 提示块标籤
{% endnote %}

{% note warning disabled %}
warning 提示块标籤
{% endnote %}

{% note danger disabled %}
danger 提示块标籤
{% endnote %}
```

{% note disabled %}
默认 提示块标籤
{% endnote %}

{% note default disabled %}
default 提示块标籤
{% endnote %}

{% note primary disabled %}
primary 提示块标籤
{% endnote %}

{% note success disabled %}
success 提示块标籤
{% endnote %}

{% note info disabled %}
info 提示块标籤
{% endnote %}

{% note warning disabled %}
warning 提示块标籤
{% endnote %}

{% note danger disabled %}
danger 提示块标籤
{% endnote %}

### no-icon

```markdown
{% note no-icon %}
默认 提示块标籤
{% endnote %}

{% note default no-icon %}
default 提示块标籤
{% endnote %}

{% note primary no-icon %}
primary 提示块标籤
{% endnote %}

{% note success no-icon %}
success 提示块标籤
{% endnote %}

{% note info no-icon %}
info 提示块标籤
{% endnote %}

{% note warning no-icon %}
warning 提示块标籤
{% endnote %}

{% note danger no-icon %}
danger 提示块标籤
{% endnote %}
```

{% note no-icon %}
默认 提示块标籤
{% endnote %}

{% note default no-icon %}
default 提示块标籤
{% endnote %}

{% note primary no-icon %}
primary 提示块标籤
{% endnote %}

{% note success no-icon %}
success 提示块标籤
{% endnote %}

{% note info no-icon %}
info 提示块标籤
{% endnote %}

{% note warning no-icon %}
warning 提示块标籤
{% endnote %}

{% note danger no-icon %}
danger 提示块标籤
{% endnote %}

## 用法二

```markdown
{% note [color] [icon] [style] %}
Any content (support inline tags too.io).
{% endnote %}
```

| 名称  | 用法                                                         |
| ----- | ------------------------------------------------------------ |
| color | 【可选】顔色<br/>(default / blue / pink / red / purple / orange / green) |
| icon  | 【可选】可配置自定义 icon (只支持 fontawesome 图标, 也可以配置 no-icon ) |
| style | 【可选】可以覆盖配置中的 style<br/>（simple/modern/flat/disabled） |

### simple

```markdown
{% note 'fab fa-cc-visa' simple %}
你是刷 Visa 还是 UnionPay
{% endnote %}
{% note blue 'fas fa-bullhorn' simple %}
2021年快到了....
{% endnote %}
{% note pink 'fas fa-car-crash' simple %}
小心开车 安全至上
{% endnote %}
{% note red 'fas fa-fan' simple%}
这是三片呢？还是四片？
{% endnote %}
{% note orange 'fas fa-battery-half' simple %}
你是刷 Visa 还是 UnionPay
{% endnote %}
{% note purple 'far fa-hand-scissors' simple %}
剪刀石头布
{% endnote %}
{% note green 'fab fa-internet-explorer' simple %}
前端最讨厌的浏览器
{% endnote %}
```

{% note 'fab fa-cc-visa' simple %}
你是刷 Visa 还是 UnionPay
{% endnote %}
{% note blue 'fas fa-bullhorn' simple %}
2021年快到了....
{% endnote %}
{% note pink 'fas fa-car-crash' simple %}
小心开车 安全至上
{% endnote %}
{% note red 'fas fa-fan' simple%}
这是三片呢？还是四片？
{% endnote %}
{% note orange 'fas fa-battery-half' simple %}
你是刷 Visa 还是 UnionPay
{% endnote %}
{% note purple 'far fa-hand-scissors' simple %}
剪刀石头布
{% endnote %}
{% note green 'fab fa-internet-explorer' simple %}
前端最讨厌的浏览器
{% endnote %}

### modern

```markdown
{% note 'fab fa-cc-visa' modern %}
你是刷 Visa 还是 UnionPay
{% endnote %}
{% note blue 'fas fa-bullhorn' modern %}
2021年快到了....
{% endnote %}
{% note pink 'fas fa-car-crash' modern %}
小心开车 安全至上
{% endnote %}
{% note red 'fas fa-fan' modern%}
这是三片呢？还是四片？
{% endnote %}
{% note orange 'fas fa-battery-half' modern %}
你是刷 Visa 还是 UnionPay
{% endnote %}
{% note purple 'far fa-hand-scissors' modern %}
剪刀石头布
{% endnote %}
{% note green 'fab fa-internet-explorer' modern %}
前端最讨厌的浏览器
{% endnote %}
```

{% note 'fab fa-cc-visa' modern %}
你是刷 Visa 还是 UnionPay
{% endnote %}
{% note blue 'fas fa-bullhorn' modern %}
2021年快到了....
{% endnote %}
{% note pink 'fas fa-car-crash' modern %}
小心开车 安全至上
{% endnote %}
{% note red 'fas fa-fan' modern%}
这是三片呢？还是四片？
{% endnote %}
{% note orange 'fas fa-battery-half' modern %}
你是刷 Visa 还是 UnionPay
{% endnote %}
{% note purple 'far fa-hand-scissors' modern %}
剪刀石头布
{% endnote %}
{% note green 'fab fa-internet-explorer' modern %}
前端最讨厌的浏览器
{% endnote %}

### flat

```markdown
{% note 'fab fa-cc-visa' flat %}
你是刷 Visa 还是 UnionPay
{% endnote %}
{% note blue 'fas fa-bullhorn' flat %}
2021年快到了....
{% endnote %}
{% note pink 'fas fa-car-crash' flat %}
小心开车 安全至上
{% endnote %}
{% note red 'fas fa-fan' flat%}
这是三片呢？还是四片？
{% endnote %}
{% note orange 'fas fa-battery-half' flat %}
你是刷 Visa 还是 UnionPay
{% endnote %}
{% note purple 'far fa-hand-scissors' flat %}
剪刀石头布
{% endnote %}
{% note green 'fab fa-internet-explorer' flat %}
前端最讨厌的浏览器
{% endnote %}
```

{% note 'fab fa-cc-visa' flat %}
你是刷 Visa 还是 UnionPay
{% endnote %}
{% note blue 'fas fa-bullhorn' flat %}
2021年快到了....
{% endnote %}
{% note pink 'fas fa-car-crash' flat %}
小心开车 安全至上
{% endnote %}
{% note red 'fas fa-fan' flat%}
这是三片呢？还是四片？
{% endnote %}
{% note orange 'fas fa-battery-half' flat %}
你是刷 Visa 还是 UnionPay
{% endnote %}
{% note purple 'far fa-hand-scissors' flat %}
剪刀石头布
{% endnote %}
{% note green 'fab fa-internet-explorer' flat %}
前端最讨厌的浏览器
{% endnote %}

### disabled

```markdown
{% note 'fab fa-cc-visa' disabled %}
你是刷 Visa 还是 UnionPay
{% endnote %}
{% note blue 'fas fa-bullhorn' disabled %}
2021年快到了....
{% endnote %}
{% note pink 'fas fa-car-crash' disabled %}
小心开车 安全至上
{% endnote %}
{% note red 'fas fa-fan' disabled %}
这是三片呢？还是四片？
{% endnote %}
{% note orange 'fas fa-battery-half' disabled %}
你是刷 Visa 还是 UnionPay
{% endnote %}
{% note purple 'far fa-hand-scissors' disabled %}
剪刀石头布
{% endnote %}
{% note green 'fab fa-internet-explorer' disabled %}
前端最讨厌的浏览器
{% endnote %}
```

{% note 'fab fa-cc-visa' disabled %}
你是刷 Visa 还是 UnionPay
{% endnote %}
{% note blue 'fas fa-bullhorn' disabled %}
2021年快到了....
{% endnote %}
{% note pink 'fas fa-car-crash' disabled %}
小心开车 安全至上
{% endnote %}
{% note red 'fas fa-fan' disabled %}
这是三片呢？还是四片？
{% endnote %}
{% note orange 'fas fa-battery-half' disabled %}
你是刷 Visa 还是 UnionPay
{% endnote %}
{% note purple 'far fa-hand-scissors' disabled %}
剪刀石头布
{% endnote %}
{% note green 'fab fa-internet-explorer' disabled %}
前端最讨厌的浏览器
{% endnote %}

### no-icon

```markdown
{% note no-icon %}
你是刷 Visa 还是 UnionPay
{% endnote %}
{% note blue no-icon %}
2021年快到了....
{% endnote %}
{% note pink no-icon %}
小心开车 安全至上
{% endnote %}
{% note red no-icon %}
这是三片呢？还是四片？
{% endnote %}
{% note orange no-icon %}
你是刷 Visa 还是 UnionPay
{% endnote %}
{% note purple no-icon %}
剪刀石头布
{% endnote %}
{% note green no-icon %}
前端最讨厌的浏览器
{% endnote %}
```

{% note no-icon %}
你是刷 Visa 还是 UnionPay
{% endnote %}
{% note blue no-icon %}
2021年快到了....
{% endnote %}
{% note pink no-icon %}
小心开车 安全至上
{% endnote %}
{% note red no-icon %}
这是三片呢？还是四片？
{% endnote %}
{% note orange no-icon %}
你是刷 Visa 还是 UnionPay
{% endnote %}
{% note purple no-icon %}
剪刀石头布
{% endnote %}
{% note green no-icon %}
前端最讨厌的浏览器
{% endnote %}

# Gallery相册图库

```html
<div class="gallery-group-main">
{% galleryGroup name description link img-url %}
{% galleryGroup name description link img-url %}
{% galleryGroup name description link img-url %}
</div>
```

| 名称        | 用法                 |
| ----------- | -------------------- |
| name        | 图库名字             |
| description | 图库描述             |
| link        | 连接到对应相册的地址 |
| img-url     | 图库封面的地址       |

> **e.g.**
>
> ```html
> <div class="gallery-group-main">
> {% galleryGroup '壁纸' '收藏的一些壁纸' '/Gallery/wallpaper' https://i.loli.net/2019/11/10/T7Mu8Aod3egmC4Q.png %}
> {% galleryGroup '漫威' '关于漫威的图片' '/Gallery/marvel' https://i.loli.net/2019/12/25/8t97aVlp4hgyBGu.jpg %}
> {% galleryGroup 'OH MY GIRL' '关于OH MY GIRL的图片' '/Gallery/ohmygirl' https://i.loli.net/2019/12/25/hOqbQ3BIwa6KWpo.jpg %}
> </div>
> ```

# Gallery相册

```
{% gallery %}
markdown 图片格式
{% endgallery %}
```

> **e.g.**
>
> ```markdown
> {% gallery %}
> ![](https://i.loli.net/2019/12/25/Fze9jchtnyJXMHN.jpg)
> ![](https://i.loli.net/2019/12/25/ryLVePaqkYm4TEK.jpg)
> ![](https://i.loli.net/2019/12/25/gEy5Zc1Ai6VuO4N.jpg)
> ![](https://i.loli.net/2019/12/25/d6QHbytlSYO4FBG.jpg)
> ![](https://i.loli.net/2019/12/25/6nepIJ1xTgufatZ.jpg)
> ![](https://i.loli.net/2019/12/25/E7Jvr4eIPwUNmzq.jpg)
> ![](https://i.loli.net/2019/12/25/mh19anwBSWIkGlH.jpg)
> ![](https://i.loli.net/2019/12/25/2tu9JC8ewpBFagv.jpg)
> {% endgallery %}
> ```

# tag-hide

## Inline

`inline` 在文本里面添加按钮隐藏内容，只限文字

```
{% hideInline content,display,bg,color %}
```

| 名称    | 用法                                              |
| ------- | ------------------------------------------------- |
| content | 文本内容<br>content不能包含英文逗号，可用`sbquo;` |
| display | 按钮显示的文字(可选)                              |
| bg      | 按钮的背景颜色(可选)                              |
| color   | 按钮文字的颜色(可选)                              |

> **e.g.**
>
> ```
> 哪个英文字母最酷？ {% hideInline 因为西装裤(C装酷),查看答案,#FF7242,#fff %}
> 
> 门里站着一个人? {% hideInline 闪 %}
> ```
>
> 哪个英文字母最酷？ {% hideInline 因为西装裤(C装酷),查看答案,#FF7242,#fff %}
>
> 门里站着一个人? {% hideInline 闪 %}

## Block

`block`独立的block隐藏内容，可以隐藏很多内容，包括图片，代码块等等

```
{% hideBlock display,bg,color %}
content
{% endhideBlock %}
```

| 名称    | 用法                                                         |
| ------- | ------------------------------------------------------------ |
| content | 文本内容                                                     |
| display | 按钮显示的文字(可选)<br> display 不能包含英文逗号，可用`&sbquo;` |
| bg      | 按钮的背景颜色(可选)                                         |
| color   | 按钮文字的颜色(可选)                                         |

> **e.g.**
>
> ```
> 查看答案
> {% hideBlock 查看答案 %}
> 傻子，怎么可能有答案
> {% endhideBlock %}
> ```
>
> 查看答案
> {% hideBlock 查看答案 %}
> 傻子，怎么可能有答案
> {% endhideBlock %}

## Toggle

如果你需要展示的内容太多，可以把它隐藏在收缩框里，需要时再把它展开

```
{% hideToggle display,bg,color %}
content
{% endhideToggle %}
```

**display 不能包含英文逗号，可用`&sbquo`**

> **e.g.**
>
> ```
> {% hideToggle Butterfly安装方法 %}
> 在你的博客根目录里
> 
> git clone -b master https://github.com/jerryc127/hexo-theme-butterfly.git themes/Butterfly
> 
> 如果想要安装比较新的dev分支，可以
> 
> git clone -b dev https://github.com/jerryc127/hexo-theme-butterfly.git themes/Butterfly
> 
> {% endhideToggle %}
> ```
>
> {% hideToggle Butterfly安装方法 %}
> 在你的博客根目录里
>
> git clone -b master https://github.com/jerryc127/hexo-theme-butterfly.git themes/Butterfly
>
> 如果想要安装比较新的dev分支，可以
>
> git clone -b dev https://github.com/jerryc127/hexo-theme-butterfly.git themes/Butterfly
>
> {% endhideToggle %}

