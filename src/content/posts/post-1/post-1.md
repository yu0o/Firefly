---
title: ESA 函数和Pages部署Firefly！ # 文章标题 (string, 必填)
published: 2026-09-05 # 发布日期 (date, 必填)
# updated:  # 更新日期 (date, 选填，未设置则默认使用发布日期)
description: 使用阿里云ESA免费部署同款博客。 # 文章简短描述，显示在首页文章卡片上 (string, 选填)
image: "api" # 封面图片路径 (string, 选填)
tags: ["ESA","教程"] # 文章标签 (string[], 选填)
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

# 使用
> 现在你应该成功部署Firefly，可以先访问测试域名查看是否正常，然后配置自己的域名就可以使用了
* `修改Firefly        待补充...`
* `评论系统自部署      待补充...`
* `音乐meting-api     待补充...`
