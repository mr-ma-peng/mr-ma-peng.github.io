---
layout: post
title: "GitHub 中的两种特殊仓库：`user-name.github.io` 与 `user-name`"
date: 2025-05-20
tags: [GitHub, GitHub Pages, README, 个人博客]
---

在 GitHub 上，有两种特殊的仓库命名方式：`user-name.github.io` 和 `user-name`。它们各自具有特定的功能和用途，尤其适用于展示个人项目、博客网站或自定义 GitHub 个人资料页面。

---

## 🏠 `user-name.github.io` —— GitHub Pages 用户/组织站点

### 🔍 主要作用

该仓库用于托管通过 **GitHub Pages** 提供的静态网站服务，是创建个人博客、作品集或文档网站的理想选择。

例如，如果您的用户名为 `mr-ma-peng`，那么您的网站将会部署在 `https://mr-ma-peng.github.io`。

### ✅ 关键特性

| 特性 | 描述 |
|------|------|
| 自动发布 | 推送代码后会自动构建并部署站点 |
| 默认域名 | 提供 `github.io` 的子域名（如 `user-name.github.io`） |
| 支持自定义域名 | 可绑定自己的域名 |
| 静态站点支持 | 支持 HTML、CSS、JavaScript 或使用 Jekyll 等静态生成器 |

> 每个 GitHub 用户或组织只能拥有一个此类仓库。

---

## 👤 `user-name` —— 个性化 GitHub 个人资料页

### 🔍 主要作用

当仓库名称与您的 GitHub 用户名完全一致时（如用户名为 `mr-ma-peng`，仓库也叫 `mr-ma-peng`），其 [README.md](file:///Users/peng.ma/GitHub/mr-ma-peng.github.io/README.md) 文件的内容将在您的 **GitHub 公共主页** 上直接展示。

这为展示个性信息、技术栈、项目链接等提供了极佳的机会。

### ✅ 关键特性

| 特性 | 描述 |
|------|------|
| 个性化展示 | 使用 Markdown 编写丰富内容 |
| 公开可见 | 所有访问您主页的人都能看到 |
| 不用于网站托管 | 仅用于增强 GitHub Profile 页面展示效果 |

---

## 📌 总结对比

| 类型 | 用途 | 是否托管网站 | 是否影响主页显示 |
|------|------|---------------|------------------|
| `user-name.github.io` | 发布公开网站 | ✅ 是 | ❌ 否 |
| `user-name` | 展示 GitHub 个人主页 | ❌ 否 | ✅ 是 |

这两种仓库都为 GitHub 用户提供了独特的展示能力，帮助我们更好地呈现技术和个人品牌。

---

📌 **建议实践**

- 如果你希望建立一个博客站点，请使用 `your-username.github.io` 命名的仓库，并启用 GitHub Pages。
- 如果你希望美化你的 GitHub 主页，请创建一个与用户名相同的仓库，并编写一份引人注目的 [README.md](file:///Users/peng.ma/GitHub/mr-ma-peng.github.io/README.md)。

---

_本文由 [Peng Ma](https://github.com/mr-ma-peng) 编写，欢迎留言交流更多 GitHub 实践技巧！_
