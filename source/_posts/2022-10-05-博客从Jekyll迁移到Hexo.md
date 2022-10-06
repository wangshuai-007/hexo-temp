---
layout:     post
title:      博客从Jekyll迁移到Hexo
date:       2022-10-05
author:     王帅
catalog: true
tags:
    - Jekyll
    - Hexo
typora-root-url: ..
---

### 引言

国庆闲来无事，打算补上之前没写的博客；碍于Jekyll的以下限制：

* 日常开发用的是Windows，Jekyll的环境略显麻烦
* 之前博客放在GitHub Page的，GitHub Page对Jekyll适配不佳，部分插件不支持
* 最近有几篇文章想做SEO，但是效果不好

打算试试其它博客方案

### 迁移步骤

#### 1.参照[网上](https://blog.csdn.net/yaorongke/article/details/119089190)教程搭建基本的Hexo博客环境,本博客使用的是[Fluid主题](https://github.com/fluid-dev/hexo-theme-fluid)

#### 2.将原博客的所有文章迁移到Hexo

Jekyll和Hexo都是静态博客网站，文章迁移很方便；将**_posts**目录下的所有文章和文章的图片目录**img**都复制到**source**路径下

执行`hexo g`、 `hexo s`预览网站，发现内容可以一个字都不用动

#### 3.发布博客

上面的教程展示的是将博客放到`GitHub Page`上 ，但我看其它文章建议把博客源码设为私有仓库（防止git的deploy密钥泄漏）;但**免费账号**的私有仓库不支持GitHub Page,于是考虑`cloudflare Page`，`cloudflare Page`的架构预设上没有`Hexo`的模板,考虑到它们都是静态博客于是使用自定义命令发布了博客:

构建命令填`hexo g`

构建输出目录填`/public`

![image-20221006104514958](/img/cloudflare_pages_custom_command.png)



#### 4.其它调整

* Jekyll和Hexo的文章生成方式略有不同，之前文章中是有`subtitle`显示在`title`之下的，但[Fluid主题](https://github.com/fluid-dev/hexo-theme-fluid)默认优先显示`subtitle`于是需要把所有文章`subtitle`去掉(或者改成`excerpt`标签)

* 参考[Fluid -4- 页脚增加网站运行时长](https://www.zywvvd.com/notes/hexo/theme/fluid/fluid-run-how-long/fluid-run-how-long/)为网站添加运行时间
* 重新在各搜索引擎上提交`sitemap.xml`


### 参考资料
  * [[Fluid主题](https://github.com/fluid-dev/hexo-theme-fluid)](https://github.com/xiaoyang-sde/reflare)
  * [Fluid -4- 页脚增加网站运行时长](https://www.zywvvd.com/notes/hexo/theme/fluid/fluid-run-how-long/fluid-run-how-long/)
