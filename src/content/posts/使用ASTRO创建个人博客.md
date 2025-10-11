---
title: 使用ASTRO创建个人博客
published: 2025-10-11
description: '一步步教学,如何创建博客'
image: ''
tags: []
category: 'Blog'
draft: true 
lang: 'zh-CN'
---

1.前置

- Node.js
- pnpm

2.生成仓库

1. 打开官方模板仓库
    https://github.com/saicaca/fuwari
2. 右上角 **Use this template → Create a new repository**
    仓库名随意（如 `my-blog`），选 Public/Private 都行
3. 克隆到本地
    git clone https://github.com/你的用户名/my-blog.git
    cd my-blog

3.安装依赖

1. pnpm install 安装全部依赖
2. pnpm add sharp 手动安装sharp
3. pnpm dev 启动服务器

4.个性化设置

5.写文章

​	pnpm new-post mypost

6.使用vercel部署

1. 打开 Vercel Dashboard（https://vercel.com/dashboard）
2. 找到你的 `SobBlog` 项目，点进去
3. 在 「Deployments」 标签页能看到一条新的构建记录，状态从
    `Building` → `Ready` 即表示线上已更新完成
