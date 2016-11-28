---
layout:	post
title:	"Jekyll+Github Pages搭建静态博客"
categories: Stuff
tags:	Jekyll RubyGems Github
author:	Tyrael_Ming
---

* content
{:toc}

由于国内各种博客平台的种种限制和不人性化，一直以来都想搭建一个属于自己的博客，好不容易最近工作落定，距离上班还有一定的时间，才重新把这个计划搬上日程。也是通过博主[http://kresnik.wang/](http://kresnik.wang/)的教程学会基本搭建。

#### 关于搭建博客
关于利用github pages搭建博客道不道德的争论一直都存在，但私以为：“Techiques don't identify themself, Users do.”

## 搭建过程

### 开启github pages

首先要对Github pages有一定了解，这是github推出的一项静态页面技术，提供用户300MB的在线空间，官方网站[https://pages.github.com/](https://pages.github.com/)对如何建立自己的github pages已经说得比较明白了，我用的是MAC OS系统，比较方便用terminal进行项目的修改。

### 部署jekyll

Jekyll的原理很简单，这是一个已经合成好的静态html网站结构。你用这个结构在你github pages的repo里面粘帖好所有文件。再把更新完的本地repo推送到GitHub的master branch里面，你的网站就更新建设完毕了。

#### 安装Ruby和RubyGems

首先你需要ruby来使用本地jekyll。Mac和Linux可以用Terminal配合yum或者brew这样的包管理器很方便的安装ruby。安装完之后可以在terminal里输入`ruby --version`来查看是否安装成功。

```
➜  ~ ruby --version
ruby 2.3.3p222 (2016-11-21 revision 56859) [x86_64-darwin16]
```

安装完ruby，之后就是要安装[RubyGems](https://rubygems.org/pages/download)，gem是一个ruby的包管理系统，可以用gem很方便的在本地安装ruby应用。

安装方法

```
//在RubyGems官网上下载压缩包，解压到你的本地任意位置
//在Terminal中
cd yourpath to RubyGems //你解压的位置
ruby setup.rb
```

有了gem之后安装jekyll就很容易了，直接在Terminal里面输入以下代码：

```
$ gem install jekyll
```

*如果不成功有可能是你没有添加 gem sources。*

如果你喜欢自己鼓捣一些前端技术，你可以自己创建jekyll的框架:

├── _config.yml   

├── _drafts

```
|   ├── begin-with-the-crazy-ideas.textile
|   └── on-simplicity-in-technology.markdown
```

├── _includes

```
|   ├── footer.html
|   └── header.html
```

├── _layouts

```
|   ├── default.html
|   └── post.html
```

├── _posts

```
|   ├── 2007-10-29-why-every-programmer-should-play-nethack.md
|   └── 2009-04-26-barcamp-boston-4-roundup.md
```

├── _site

└── index.html
你可以一个个依次建立起来，然后在自己编写一个你想要的博客。

或者你可以去[jekyll themes](http://jekyllthemes.org/)寻找自己喜欢的模板，手残党福利。

下载完了模板，可以吧里面的内容解压到你自己的网站目录底下。这时候你可以测试一下：

```
$ cd you website path //cd到你的网站目录下
$ jekyll serve
//一个开发服务器将会运行在 http://localhost:4000/
//你就能在本地服务器看到你用模板搭建的网站了
```

所有的文章直接放在_posts文件夹下面，格式就是markdown文件，默认的格式是.md和.markdown文件。到此为止可以开始尽情的写博客了，用GitHub软件同步到你的repository里面，网站上面就可以进行正常的显示了。

