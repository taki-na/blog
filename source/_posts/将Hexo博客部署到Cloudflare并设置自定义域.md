---
title: 将Hexo博客部署到Cloudflare并设置自定义域
data: 
updata: 
top_img: http://img.xjh.me/random_img.php?ctype=acg&return=302
cover: http://img.xjh.me/random_img.php?ctype=acg&return=302
categories:
- 教程
tags:
- Cloudflare
- Hexo
- 教程
---

## 前言
使用Hexo搭建博客的教程非常多，在此就不再赘述，具体可以查看[这篇文章](https://zhuanlan.zhihu.com/p/60578464)。

### 必要条件
1. 已将Hexo博客上传到Github。
2. 拥有Cloudflare账户，如无账户请前往[Cloudflare官网](https://www.cloudflare.com)注册

## 正文
### 部署到Cloudflare
登录[Cloudflare控制面板](https://dash.cloudflare.com/)  
进入"Pages"页面  
点击“创建项目”，再点击“连接到Git”  
授权Cloudflare访问你的Github库  
选择储存你的博客的库  
项目名称随便取个名字，生产分支选择你存放博客文件的分支（一般是master)  
![](https://s2.loli.net/2022/07/25/LAg5l6sFiQpJjDZ.jpg)
点击“保存并部署”，部署成功后点击这个链接即可访问
![](https://s2.loli.net/2022/07/25/PON6J8smhRyKd9v.jpg)
### 设置自定义域（可选）
进入"Pages"页面->自定义域->设置自定义域  
输入你的域名，点击继续，点击激活域
稍等片刻，即可使用自己的域名访问博客了
## 结语
第一次写博客，文笔较差请谅解  
偶然间发现cf有这种功能，于是就写出来记录一下