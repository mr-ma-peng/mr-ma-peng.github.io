---
layout: default
title: "使用 GitHub Pages + Jekyll + minimal 构建个人博客"
date: 2025-05-19
tags: [GitHub Pages, Jekyll, minimal, 博客搭建]
---

GitHub Pages 是一个免费托管静态网站的服务，配合 Jekyll 博客框架和官方提供的 `minimal` 主题，可以非常轻量地搭建个人博客。本文记录我的搭建过程和配置要点。

---

## 🛠️ 第一步：创建仓库

1. 创建一个公开仓库，命名为：`your-username.github.io`
2. 进入仓库设置，启用 GitHub Pages：
   - 选择部署分支为 `main`
   - 根目录作为发布源

---

## 📦 第二步：配置 Jekyll 和 minimal 主题

在项目根目录下创建 `_config.yml`，内容如下：

```yaml
title: 我的博客
description: 记录我的技术成长之路
remote_theme: pages-themes/minimal@v0.2.0
plugins:
  - jekyll-remote-theme
