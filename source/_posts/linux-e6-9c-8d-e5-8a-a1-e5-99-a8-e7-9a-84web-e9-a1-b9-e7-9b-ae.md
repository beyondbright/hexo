---
title: linux服务器的web项目
tags:
  - autoComplete
  - java
  - linux
  - ssh
  - 服务器
  - 编码
id: 139
categories:
  - 工作
date: 2012-06-10 00:41:29
---

老头催着这周上线，周末加班给他解决问题，蛋疼啊。

这个项目是web项目，开发是在windows下用的是eclipse。有个功能是智能提示（如同百度搜索时，输入一个字或者词语下拉列出关联匹配的词句），用的是autoComplete的js插件，在内网的windows下的服务器完全木有问题，一旦放到外网linux就悲催了，百般折腾，搞了一个下午，最后发现是编码问题。。。。

目前为止发现放到linux服务器时容易忽略的问题有：

1、大小写问题

2、编码问题

3、引号问题