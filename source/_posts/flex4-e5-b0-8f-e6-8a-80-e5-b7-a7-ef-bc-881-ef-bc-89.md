---
title: flex4小技巧（1）
id: 62
categories:
  - flash编程
date: 2011-11-10 23:34:14
tags:
---

1、webgame的主swf文件大小优化，将大图或者比较少用的图片放服务器，需要用的时候在从服务器取。hula因此直接从4M降到2M！

2、UIcomponent 继承 Sprite ， 两者都继承 DisplayObject。继承UIcomponent的container将addChild方法重写，必须addChild实现IUIcomponent的组件，所以container不能直接addChild类似Sprite的displayObject。Sprite不能直接addChild继承UIcomponent的flex组件，因为flex组件需要layout，所以它的parent必须是实现IUIcomponent的容器，所以Sprite作为它的parent不会报错，但也不会显示！

3、只侦听一个enterFrame。

4、bitmapdata不用了就dispose掉吧