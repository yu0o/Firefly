---
title: ESA 函数和Pages部署Firefly！ # 文章标题 (string, 必填)
published: 2026-09-05 # 发布日期 (date, 必填)
# updated:  # 更新日期 (date, 选填，未设置则默认使用发布日期)
description: 使用阿里云ESA免费部署同款博客。 # 文章简短描述，显示在首页文章卡片上 (string, 选填)
image: "api" # 封面图片路径 (string, 选填)
tags: ["阿里云","教程"] # 文章标签 (string[], 选填)
category: 教程 # 文章分类 (string, 选填)
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
passwordHint: 请输入密码 # 密码提示，显示在密码输入框上方 (string, 选填)
series: Firefly   # 所属系列名称，文章页正文上方会显示可折叠的系列导航 (string, 选填)
seriesOrder: 1 # 系列中的排序序号 (number, 选填)
---

# 部署前提
* 一个开通了ESA的阿里云账号
* Github账号
> 阿里云边缘安全加速 ESA（Edge Security Acceleration），是一款将网络加速与安全防护深度融合的全球化服务。  
> 一般来说免费版本已经足够正常使用了，自行开通免费版。
# 部署步骤

1. [Fork](https://github.com/CuteLeaf/Firefly/fork) Github仓库
2. 登录 阿里云 ESA 控制台
3. 进入 Pages 功能，点击 创建项目，[一键直达](https://esa.console.aliyun.com/edge/pages/creation)
4. 选择 从 Git 仓库导入，连接刚刚Github Fork的仓库
    * 配置构建设置：
    * 安装命令: `pnpm install`
    * 构建命令: `pnpm build`
    * 根目录: `/`
    * 静态资源目录: `./dist`
    * Node.js 版本: `22.xx`        
5. 点击 `开始部署`
![配置图片](./pages.png)
:::TIP
原作者也提供了部署教程可以点击 [跳转](https://docs-firefly.cuteleaf.cn/zh/guide/deploy.html#%E9%98%BF%E9%87%8C%E4%BA%91-esa)
:::

# 使用建议
> 现在你应该成功部署Firefly，可以先访问测试域名查看是否正常，然后配置自己的域名就可以使用了
## 修改Firefly
> 这个在Firefly的文档中已经很简单明确了       
> 乍一看可能很麻烦 耐心看完很简单的 [点击跳转](https://docs-firefly.cuteleaf.cn/zh/guide/getting-started.html)        
> 主要就是修改下面的目录
```
Firefly/
├── src/
│   ├── config/          # 配置文件目录
│   ├── components/      # 组件目录
│   ├── content/         # 内容目录（文章、页面）
│   ├── layouts/         # 布局模板
│   ├── pages/           # 页面路由
│   └── types/           # 类型定义
├── public/              # 静态资源
└── astro.config.mjs     # Astro 配置
```

## 部署Music Meting-API
这边推荐使用由`mikus-loli`优化版本 该项目Fork自`xizeyoupan/Meting-API`
> Meting-API
> 多平台音乐 API 服务，支持网易云音乐和 QQ 音乐，提供完整的 Cookie 管理、VIP 歌曲播放、自动续期和监测通知功能。
> 功能特性
> - 双平台支持：网易云音乐、QQ 音乐
> - Cookie 管理系统：增删改查、在线验证、VIP 播放能力检测
> - QQ 音乐 Cookie 自动刷新：支持 musickey 和 refresh_token 两种续期方式
> - Cookie 定时监测：可配置间隔自动检查，失效/VIP 丢失时自动通知
> - Webhook 通知：兼容 Gotify、企业微信、钉钉、飞书等
> - 2FA 双因素认证：TOTP 实现，兼容 Google Authenticator
> - 用户与权限管理：多用户、角色区分、登录失败锁定
> - 管理后台：功能完备的单页应用，响应式设计
> - 多运行时部署：Node.js / Docker / Vercel / Cloudflare Workers
> - Docker 多架构镜像：支持 amd64/arm64，自动 CI/CD 发布
> 
::github{repo="mikus-loli/Meting-API"}
> 成功部署好自己的meting-api之后      
> 在**Firefly/src/config/** 修改**musicConfig.ts** 音乐配置为自己的即可        
> 自己部署的可以添加**vip cookie**当然你也可以使用别人的api

## 评论系统(twkikoo)
**firefly**支持的评论系统有`Twikoo`、`Waline`、`Giscus`、`Disqus` 和 `Artalk`。     
部署后在**Firefly/src/config/** 修改**commentConfig.ts** 评论系统配置为自己的即可
> 我这边最终选择了 **Twikoo**  支持云函数部署和docker一键部署   
> **云函数部署** [点击这里](https://twikoo.js.org/quick-start.html) 查看详细教程   
>    
> **docker**一键部署
> ```docker
> docker run --name twikoo -e TWIKOO_THROTTLE=1000 -p 8080:8080 -v ${PWD}/data:/app/data -d imaegoo/twikoo
> ```
