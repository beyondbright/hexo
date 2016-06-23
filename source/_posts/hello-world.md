---
title: Hexo + Github 搭建博客
date: 2016-06-11
tags: Other
---
> 本文涉及知识点：
> [Hexo](https://hexo.io)
> [Github](https://github.com)
> 本文作者使用的系统是 **Ubuntu 16.04**

### Github
- 登录[Github](https://github.com)后，点击右下角[New repository](https://github.com/new)创建仓库，**Repository name**必须按照*xxx.github.io*格式填写，这样该仓库才是*xxx.github.io*域名对应的空间（参考[GithubPages](https://pages.github.com)）。

![new repository](http://o8nhgt9v5.bkt.clouddn.com/create%20a%20new%20repository.png)
- 安装[Git](https://git-scm.com)
```bash
apt-get install git
```
- 用[SSH](https://help.github.com/categories/ssh/)验证授权。添加*id_rsa.pub*内容到Github上，*Setting -> SSH and GPG keys -> New SSH key -> Key -> Add SSH key*。
```bash
apt-get install ssh
ssh-keygen -t rsa
cd ~/.ssh
cat id_rsa.pub
```
![github页面](http://o8nhgt9v5.bkt.clouddn.com/ssh.png)
- 测试SSH配置的代码：
```bash
ssh -T git@github.com
```

### Hexo
- 安装[Nodejs](https://nodejs.org)
```bash
apt-get install nodejs
```
- 安装[Hexo](https://hexo.io)
```bash
mkdir ~/blog
cd ~/blog
sudo npm install -g hexo
hexo init
```
- 测试Hexo
```bash
cd ~/blog
hexo generate
hexo server
```
- 浏览器输入：*http://localhost:4000* 进行验证
- 自动部署到github上
```bash
cd ~/blog
npm install hexo-deployer-git --save
vim _config.yml
```
- 找到deploy行进行修改，repo就是之前创建的Github的仓库
```
depoy:
  type: git
  repo: git@github.com:xxx/xxx.github.io.git
  branch: master
```
- 部署到Github上
```bash
hexo deploy
```
- 浏览器输入：*http://xxx.github.io* 进行验证
- 安装主题[NexT](http://theme-next.iissnan.com/)
- 如果是用vim编辑内容的话，推荐一个[实时预览的插件](https://github.com/suan/vim-instant-markdown)
