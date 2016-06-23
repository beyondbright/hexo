---
title: Android Studio 设置
date: 2016-06-12 17:52:41
tags: Android
---
> 本文涉及知识点：
> *Android Studio*
> 本文作者使用的系统是 **Ubuntu 16.04**

现在的Android开发者肯定知道Android Studio，相关的基本教程网上也是很多了。本文主要是作者自己的一些设置的记录。

- [基本设置](http://o8nhgt9v5.bkt.clouddn.com/settings.jar)，作者之前用Eclipse写Java和Android，所以这里的大部分keymap是用了Eclipse的。这里的设置适用于Eclipse转AS的同学。
- 设置java文件的Copyright路径 ： *setting -> File and Code Templates -> Includes -> File Header*
```java
/**
 * Copyright (c) ${YEAR}, Bongmi
 * All rights reserved
 * Author: beyondbright@gmail.com
*/ 
```
- Ubuntu版本添加中文输入法，在studio.sh启动文件头部添加export
```
export XMODIFIERS="@im=fcitx"
export GTK_IM_MODULE="fcitx"
export QT_IM_MODULE="fcitx"
```
![studio.sh](http://o8nhgt9v5.bkt.clouddn.com/1.png)
- 这里推荐一个在Android Studio上的[翻译插件](https://github.com/Skykai521/ECTranslation)
