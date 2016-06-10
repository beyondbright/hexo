---
title: 横版flash游戏引擎flixel入门
tags:
  - flash编程
  - flixel
  - 入门
  - 引擎
id: 66
categories:
  - flash编程
date: 2011-11-14 01:14:37
---

[caption id="attachment_83" align="aligncenter" width="204" caption="很强大的横版2d游戏引擎"][![](http://www.wjunjie.com/wp-content/uploads/2011/11/images.jpg "Flixel")](http://www.wjunjie.com/wp-content/uploads/2011/11/images.jpg)[/caption]最近找了个横版引擎flixel来研究下，发现确实是蛮不错的一个引擎，入门很简单，而且功能强大，基本小时候玩的横版2d游戏都能做，我怀疑男人系列是不是也用这个引擎来做~

上一篇安装好了FB4.5，现在就来个最简单的hello world吧~~

1、下载Flixel引擎（地址：https://github.com/AdamAtomic/flixel/zipball/master）后将org目录copy到新项目的src下。

2、建Flixe主程序，是继承FlxGame的，这是整个程序的入口。
[cc lang="actionscript3"]
package
{
    import org.flixel.*;
    public class FlixelGame extends FlxGame
    {
        public function FlixelGame()
        {
            //参数：长，宽，程序第一个状态（一般是目录）
            super(400,300,MenuState);
        }
    }
}
[/cc]

3、MenuState内容：
[cc lang="actionscript3"]
package
{
    import org.flixel.*;
    public class MenuState extends FlxState
    {
        //创建该状态时执行该方法
        override public function create():void
        {
            //设置背景颜色
            FlxG.bgColor = 0xFF000000;
            //添加文本说明
            var t:FlxText;
            t = new FlxText(0,FlxG.height/2-20,FlxG.width,"this is MENU!");
            //文本大小
            t.size = 32;
            //文本位置
            t.alignment = "center";
            //显示文本
            add(t);
            //显示鼠标
            FlxG.mouse.show();
        }
        //每帧刷新页面都执行该方法
        override public function update():void
        {
            super.update();
            //如果点击鼠标，切换到另一状态（一般是游戏状态）
            if(FlxG.mouse.justPressed())
                FlxG.switchState(new PlayState());
        }
    }
}
[/cc]

4、PlayState内容：
[cc lang="actionscript3"]
package
{
    import org.flixel.*;
    public class PlayState extends FlxState
    {
        //最简单的显示hello world~~
        override public function create():void
        {
            FlxG.framerate = 50;
            FlxG.flashFramerate = 50;
            var t:FlxText;
            t = new FlxText(0,FlxG.height/2-20,FlxG.width,"hello world!");
            t.size = 32;
            t.alignment = "center";
            add(t);
        }
    }
}
[/cc]

Flixel入门真的很简单，不过要用好它，并且做出一个性能很好的游戏可就不简单了哦~