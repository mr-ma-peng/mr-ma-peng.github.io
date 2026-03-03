# Contract: 博客文章 Front Matter

**Feature**: 001-speckit-cursor-mac-guide  
**Purpose**: 定义本特性交付文章所遵循的 Jekyll 文章 front matter 约定，与站点既有文章一致。

## 约定

本特性新增的博客文章 MUST 在文件顶部包含以下 YAML front matter：

```yaml
---
layout: post
title: "<文章标题>"
date: YYYY-MM-DD
tags: [标签1, 标签2, ...]
---
```

- **layout**: 固定为 `post`（站点统一使用 `layout: post`）
- **title**: 字符串，建议双引号包裹；与正文主题一致
- **date**: 与文件名中的日期一致，格式 `YYYY-MM-DD`
- **tags**: 数组，建议包含与 Spec-Kit、Cursor、Mac、需求等相关的标签

## 与现有文章的一致性

站点内现有文章（如 `_posts/2025-05-20-open-source-license.md`、`_posts/2025-06-03-prompt-engineering-thinking.md`）均采用上述结构；本文章遵循同一契约，无需扩展字段。
