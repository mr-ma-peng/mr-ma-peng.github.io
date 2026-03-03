# Data Model: Mac 上 Spec-Kit + Cursor 开发需求指南（博客文章）

**Feature**: 001-speckit-cursor-mac-guide  
**Phase**: 1 — Design

本特性交付物为单篇博客文章，无数据库或运行时数据模型；此处描述「文章」作为内容实体的结构与校验规则。

## 实体：博客文章 (Post)

### 存储形式

- **位置**: `_posts/YYYY-MM-DD-speckit-cursor-mac-guide.md`（日期与 slug 按 Jekyll 约定）
- **格式**: 单一 Markdown 文件，由 YAML front matter + 正文组成

### Front Matter 字段（与 contracts 一致）

| 字段 | 类型 | 必需 | 说明 |
|------|------|------|------|
| layout | string | 是 | 固定为 `post` |
| title | string | 是 | 文章标题，双引号包裹 |
| date | string | 是 | 发布日期，格式 YYYY-MM-DD |
| tags | array | 是 | 标签列表，如 [Spec-Kit, Cursor, Mac, 需求] |

### 正文结构（推荐层次）

- **引言**: 1–2 段，说明文章目的与受众
- **主体**: 若干二级标题（`##`）章节，建议覆盖：
  - Mac 环境（如有前置条件）
  - Spec-Kit 简介与使用方式
  - Cursor 的参与方式
  - 开发需求/规格工作流（步骤化）
- **可选**: 小结或参考链接

### 校验规则（来自需求与宪章）

- 不得包含真实 token、密钥、API Key；占位处必须使用 `******` 或明确占位符
- 正文须具备可读的标题层级，便于按步骤阅读
- 文件名与 `date` 一致，且符合 `YYYY-MM-DD-<slug>.md`

## 关系与状态

- 文章与站点为「包含」关系：单篇文章属于 `_posts` 集合，由 Jekyll 渲染后出现在博客列表与详情页
- 无状态机；发布即通过 Git 提交并经由 GitHub Actions 部署
