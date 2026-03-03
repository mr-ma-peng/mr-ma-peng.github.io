# Implementation Plan: Mac 上 Spec-Kit + Cursor 开发需求指南（博客文章）

**Branch**: `001-speckit-cursor-mac-guide` | **Date**: 2025-02-25 | **Spec**: [spec.md](./spec.md)  
**Input**: Feature specification from `specs/001-speckit-cursor-mac-guide/spec.md`

**Note**: 技术栈使用现有站点（Jekyll + minimal + GitHub Pages），风格与既有文章保持一致。

## Summary

新增一篇博客文章，主题为「在 Mac 上使用 Spec-Kit（speckit）与 Cursor 进行开发需求指南」。交付物为单篇 Markdown 文章，置于 `_posts/`，采用站点既有 Jekyll 布局与 minimal 主题，正文覆盖 Mac 环境、Spec-Kit 使用、Cursor 参与方式、以及开发需求/规格工作流；遵循项目宪章（无敏感数据、占位符使用 `******`）。

## Technical Context

**Language/Version**: Markdown（Jekyll 约定）  
**Primary Dependencies**: Jekyll、GitHub Pages、remote_theme: pages-themes/minimal@v0.2.0  
**Storage**: 文件系统，单文件 `_posts/YYYY-MM-DD-<slug>.md`  
**Testing**: 人工验收（列表可见、正文渲染、无敏感信息）；可选本地 `bundle exec jekyll serve` 预览  
**Target Platform**: GitHub Pages（静态站点）；读者环境为 Mac  
**Project Type**: static-site / content（单篇博客）  
**Performance Goals**: N/A（内容交付）  
**Constraints**: 宪章「禁止敏感数据」、占位符 `******`；文件名与 front matter 符合 Jekyll 约定  
**Scale/Scope**: 单篇新文章，与现有 5 篇文章并列

## Constitution Check

*GATE: Must pass before Phase 0 research. Re-check after Phase 1 design.*

| 原则 | 符合性 | 说明 |
|------|--------|------|
| I. 禁止敏感数据 | ✅ Pass | 文章不包含 token、密钥、API Key；示例或占位一律使用 `******` |
| II. 公开内容与可维护性 | ✅ Pass | 单篇公开文章，结构清晰、可读可维护 |
| Security & Data | ✅ Pass | 提交前自检无敏感信息；占位符规范在 research/data-model 中落实 |
| Development Workflow | ✅ Pass | 遵循 Jekyll 与 minimal 约定，Constitution Check 已验证 |

无违规，无需 Complexity Tracking。

## Project Structure

### Documentation (this feature)

```text
specs/001-speckit-cursor-mac-guide/
├── plan.md              # 本文件
├── research.md          # Phase 0：技术栈与风格决策
├── data-model.md        # Phase 1：文章实体与结构
├── quickstart.md        # Phase 1：撰写与验收步骤
├── contracts/           # Phase 1：文章 front matter 约定
└── tasks.md             # Phase 2：由 /speckit.tasks 生成
```

### Source Code (repository root)

本特性不新增代码目录，仅新增一篇内容文件：

```text
_posts/
└── YYYY-MM-DD-speckit-cursor-mac-guide.md   # 本特性唯一交付物
```

**Structure Decision**: 沿用现有博客仓库结构；仅向 `_posts/` 增加一篇 Markdown，无 `src/`、无后端/前端代码，与现有文章（如 `2025-06-03-prompt-engineering-thinking.md`）一致。

## Complexity Tracking

不适用（无宪章违规）。
