# Research: Mac 上 Spec-Kit + Cursor 开发需求指南（博客文章）

**Feature**: 001-speckit-cursor-mac-guide  
**Phase**: 0 — Outline & Research

## 1. 技术栈与站点沿用

**Decision**: 使用现有技术栈，不引入新框架或构建工具。

- **Stack**: Jekyll + GitHub Pages + remote_theme `pages-themes/minimal@v0.2.0`
- **内容格式**: Markdown，存放于 `_posts/`，文件名 `YYYY-MM-DD-<slug>.md`

**Rationale**: 用户明确要求「技术站使用现有的，风格保持一致」；现有站点已稳定运行，无需变更。

**Alternatives considered**: 使用其他静态生成器或主题 — 已拒绝，以保持与现有文章一致。

---

## 2. 文章风格与结构

**Decision**: 与既有博客文章保持同一风格与结构。

- **Front matter**: `layout: post`，`title`（双引号字符串），`date`（YYYY-MM-DD），`tags`（数组）
- **正文**: 开篇简短引言（1–2 段），随后用 `##` 二级标题分节，节间用 `---` 分隔；步骤用有序列表或 `###` 子节；代码/配置用 fenced code block（注明语言）
- **语气**: 中文、技术向但可读；适当使用 emoji 与加粗（与现有文章如 `2025-06-03-prompt-engineering-thinking.md`、`2025-05-19-github-pages-jekyll-minimal.md` 一致）

**Rationale**: 风格一致降低读者认知负担，便于维护。

**Alternatives considered**: 使用不同标题层级或无 emoji — 已拒绝，以保持全站统一。

---

## 3. 敏感信息与占位符

**Decision**: 全文遵守项目宪章；任何涉及密钥、Token、API Key 的示例一律使用 `******` 或明确占位符（如 `YOUR_***_HERE`），不出现真实或易猜示例值。

**Rationale**: 宪章 I 与 Security & Data 明确要求；仓库公开，必须从源头避免泄露。

**Alternatives considered**: 使用假示例值（如 `sk-xxx`）— 已拒绝，宪章要求统一使用 `******`。

---

## 4. 内容范围与受众

**Decision**: 文章面向「在 Mac 上想用 Spec-Kit（speckit）与 Cursor 做开发需求/规格」的读者；覆盖 Mac 环境、Spec-Kit 用途与基本使用、Cursor 的参与方式、以及从需求到规格的实操指南（可含命令与路径说明，占位符用 `******`）。

**Rationale**: 与 spec 中 FR-003、User Story 1/3 一致；不扩大为通用 Cursor 或 Mac 教程。

**Alternatives considered**: 仅写 Spec-Kit 或仅写 Cursor — 已拒绝，规格要求四类主题均覆盖。
