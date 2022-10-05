---
layout:     post
title:      octopus deploy 使用XML 配置变量功能设置nlog日志
subtitle:   octopus deploy use XML configuration variables feature set nlog config file
date:       2022-5-7
author:     王帅
catalog: true
tags:
    - octopus
    - nlog
    - config
    - xml
typora-root-url: ..
---

### 引言

项目中使用了`nlog`记录日志,现在运行的项目太多了;日志也太多

线上环境出现问题后经常需要到不同的服务器上查看各种日志,而且传统的文件日志方式很不便于查找问题,因此考虑使用[Seq — centralized structured logs](https://datalust.co/seq)



要以无侵入的方式启用线上环境的日志功能，就需要在发布工具`octopus`上做文章了.



恰好`octopus`也提供了相应的设置功能`Configuration transforms`和`Substitute Variables in Files`



本人所用`octopus`版本为`v2018.1.5`新版本可能操作略有不同,但功能肯定已包含

### 解决方案

* 添加`nlog`配置参数

在`Library`→`Variable Sets`中添加一组参数集(此处为`Seq日志全局设置`)

![octopus_add_variableSets](/img/octopus_add_variableSets)

* 为项目添加新建的参数集

在`Projets`→`Variables`→`Library Sets`中添加刚刚创建的参数集

![octopus_use_variableSets](/img/octopus_use_variableSets.png)

* 

### 参考资料
* [https://stackoverflow.com/questions/10262231/obtaining-exitcode-using-start-process-and-waitforexit-instead-of-wait](https://stackoverflow.com/questions/10262231/obtaining-exitcode-using-start-process-and-waitforexit-instead-of-wait)
* [https://stackoverflow.com/questions/3382082/whats-the-nohup-on-windows](https://stackoverflow.com/questions/3382082/whats-the-nohup-on-windows)
* [https://stackoverflow.com/questions/6604089/dynamically-generate-command-line-command-then-invoke-using-powershell](https://stackoverflow.com/questions/6604089/dynamically-generate-command-line-command-then-invoke-using-powershell)
* [https://github.com/dotnet/runtime/issues/2688#issuecomment-339577646](https://github.com/dotnet/runtime/issues/2688#issuecomment-339577646)

