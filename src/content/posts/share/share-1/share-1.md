---
title: 每月2-3¥拿下阿里云国内ECS服务器 # 文章标题 (string, 必填)
published: 2026-09-05 # 发布日期 (date, 必填)
# updated:  # 更新日期 (date, 选填，未设置则默认使用发布日期)
description: 仅需140¥可以购买阿里云国内ecs五年服务器，可用于ICP备案。 # 文章简短描述，显示在首页文章卡片上 (string, 选填)
image: "api" # 封面图片路径 (string, 选填)
tags: ["阿里云","分享"] # 文章标签 (string[], 选填)
category: 分享 # 文章分类 (string, 选填)
draft: false # 是否为草稿，草稿不会对读者可见 (boolean, 选填，默认 false)
pinned: false # 是否置顶在文章列表顶部 (boolean, 选填，默认 false)
# slug:  # 自定义 URL 路径 (string, 选填)
lang: zh-CN # 文章语言代码，如 zh-CN，仅当与站点默认语言不同时设置 (string, 选填)
author: 李安之之 # 文章作者 (string, 选填)
comment: true # 是否启用评论 (boolean, 选填，默认 true)
licenseName: MIT # 自定义许可证名称 (string, 选填)
licenseUrl: https://opensource.org/licenses/MIT # 自定义许可证链接 (string, 选填)
# sourceLink:  # 文章来源链接 (string, 选填)
# password:  # 文章密码，设置后文章将被加密保护 (string, 选填)
# passwordHint: 请输入密码 # 密码提示，显示在密码输入框上方 (string, 选填)
series: 推荐   # 所属系列名称，文章页正文上方会显示可折叠的系列导航 (string, 选填)
seriesOrder: 2 # 系列中的排序序号 (number, 选填)
---

# 介绍
:::note
国内ECS配置是`2C` `0.5GB` `2GB` `20GB`分别表示`CPU` `内存` `存储空间` `每月流量`    
超出流量使用阶梯计费，流量<10Tb `0.8¥/GB`，由于配置问题只能使用`alpine-mini`系统  
我个人是用作`frp`，`Komari`，`danmu-api`  
国外ECS配置相同但每月流量为`200GB` 按量计费`¥0.1392/1天`   
国外ECS抢占式实例，人多会被停机。我使用的是新加坡的ECS,目前一个月1-2次,其他热门地区可能更加频繁。
目前可以用作 :spoiler[**不可言说的神秘力量**]！`hubproxy` (Github,Docker加速) 
只适合轻量使用!!! 请自行考虑是否使用。 
:::
# 准备
* 略懂linux命令
* 阿里云账号
* alpine-mini镜像
    > 镜像来自于网络，[点击下载](https://hihh.lanzouw.com/iS5Bl46wazcf)   
    > ssh：`22`     
    > user：`root`    
    > password：`luminous`
# 开始
:::TIP
有空再写详细的，先看原作者教程  
文字教程：[跳转](https://blog.020915.xyz/archives/aliyun)    
视频教程：[Bilibili](https://b23.tv/6pzObsM)
:::