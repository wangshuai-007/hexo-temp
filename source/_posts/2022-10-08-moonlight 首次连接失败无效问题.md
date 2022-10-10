---
layout:     post
title:      moonlight 首次连接失败/无效问题
date:       2022-10-08
updated:    2022-10-08 
author:     王帅
catalog: true
tags:
    - moonlight
typora-root-url: ..
---

### 引言

moonlight 串流自己PC玩游戏确实感觉非常舒适,这让ipad的功能更上一个台阶;但我之前却经常遇到首次连接问题。



表现为，输入验证码后moonlight无任何变化（锁还在）

### 解决方案

#### 1.从贴吧的帖子可知，降级GeForce Experience 的版本到[v3.22](https://us.download.nvidia.cn/GFE/GFEClient/3.22.0.32/GeForce_Experience_v3.22.0.32.exe)可以连接，只要连接成功后可以再升级GeForce Experience

但每次连接新设备需要重新卸载安装再升级还是太麻烦了,通过官方讨论组:[discord](http://moonlight-stream.org/discord)我找到了另一个解决方法

#### 2.勾选控制面板→区域设置中的Beta版:使用Unicode UTF-8提供全球语言支持

![image-20221010093738011](/img/moonlingt_region.png)

首次连接失败的问题就在于,我的windows是用中文昵称登陆的,而新版本的GeForce Experience在登陆时会使用用户路径,所以登陆失败

详情可查看[Github issue #30](https://github.com/moonlight-stream/nvidia-gamestream-issues/issues/30#issuecomment-1172924002)


### 参考资料
  * ["PC not paired" issue with non-ASCII character in username #30](https://github.com/moonlight-stream/nvidia-gamestream-issues/issues/30#issuecomment-1172924002)
