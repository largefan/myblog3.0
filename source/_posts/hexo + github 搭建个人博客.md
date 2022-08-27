---
title: hexo + github 搭建个人博客
comments: true
toc: true
cover: https://s1.imagehub.cc/images/2022/08/27/hexo.png
categories: hexo
tags:
  - 个人博客
abbrlink: 1
date: 2021-10-1 00:00:00
---

## hexo + github 搭建个人博客

### 1、检查是否安装node、npm、git

* node -v
* npm -v
* git --version

### 2、Hexo下载

* npm install hexo-cli -g
* hexo -v

### 3、搭建仓库

* 仓库名字 要与 账号用户名字一致

<img src="https://img-blog.csdnimg.cn/85702601d6cd4ed093b7eef6009c60f7.png" style="zoom:67%;"/>

### 4、创建仓库后，生成ssh keys

* **如未生成过**，则在git bash里输入：ssh-keygen -t rsa -C "邮箱地址"

* 之前**已经生成过**，如图：

<img src="https://img-blog.csdnimg.cn/ff0082f6bba944ac81011df43ac303ec.png" style="zoom:67%;"/>

* 把公钥填入这里

<img src="https://img-blog.csdnimg.cn/94ff923ac6204a1ab24d7215af3ce6cc.png" style="zoom:67%;"/>

### 5、本地生成博客内容

* 在本地创建一个文件夹**(此时里面什么都没)**，右键打开git bash

* 输入：npm install -g hexo   <!--意思是安装hexo-->

* hexo init  <!--初始化后里面出现躯壳 如图-->

  <img src="https://img-blog.csdnimg.cn/a09175981787444cbc16083a6ca365bd.png" style="zoom:67%;"/>

  <img src="https://img-blog.csdnimg.cn/46311117c2ad4b5c8fac4602fdfd71a5.png" style="zoom:67%;"/>

* hexo s `<!--启动服务器输入：http://localhost:4000/-->`

* npm run server <!--启动本地服务器-->

<img src="https://img-blog.csdnimg.cn/68e484438dd64bce80c22933481deb7a.png" style="zoom:67%;"/>

### 6、把博客部署到github

* ```
  deploy:
     type: git
     repository: https://github.com/largefan/largefan.github.io.git
     branch: main
  ```

  

  <img src="https://img-blog.csdnimg.cn/dcd838b45e374dc3b67781c30c4e59ee.png" style="zoom:67%;"/>

<img src="https://img-blog.csdnimg.cn/930a94ed832d406eb7202a19f9273399.png" style="zoom:67%;"/>

<img src="https://img-blog.csdnimg.cn/7301aa70bc8a439f8ac62d5b023f9e2b.png" style="zoom:67%;"/>

* 修改完成后，右键打开git bash

* 安装hexo-deployer-git 自动部署发布工具：npm install hexo-deployer-git --save

* 建议先 hexo clean 清理一下

* 然后输入生成页面命令： hexo g

* 然后把本地文件上传到github仓库 命令：hexo d

* 然后令牌没问题就可以访问了：https://largefan.github.io/

  <img src="https://img-blog.csdnimg.cn/3857a5af8a48483388b66305f54aadde.png" style="zoom:67%;"/>
