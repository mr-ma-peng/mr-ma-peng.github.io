# Quickstart: 撰写并发布「Mac 上 Spec-Kit + Cursor 开发需求指南」文章

**Feature**: 001-speckit-cursor-mac-guide  
**Purpose**: 按计划完成单篇博客的撰写、自检与发布。

## 前置条件

- 仓库已克隆，当前分支为 `001-speckit-cursor-mac-guide`
- 已阅读 [spec.md](./spec.md)、[research.md](./research.md)、[data-model.md](./data-model.md) 与 [contracts/post-front-matter.md](./contracts/post-front-matter.md)

## 步骤

### 1. 创建文章文件

- 在 `_posts/` 下新建文件，命名：`YYYY-MM-DD-speckit-cursor-mac-guide.md`（日期取计划发布日期）
- 按 [contracts/post-front-matter.md](./contracts/post-front-matter.md) 填写 front matter（layout、title、date、tags）

### 2. 撰写正文

- 按 [research.md](./research.md) 与 [data-model.md](./data-model.md) 中的结构与风格撰写
- 必须覆盖：Mac 环境、Spec-Kit、Cursor、开发需求/规格工作流
- 全文不得出现真实 token/密钥/API Key；占位一律使用 `******` 或明确占位符
- 使用 `##`、`###` 与 `---` 保持层次清晰，与现有文章风格一致

### 3. 本地预览（可选）

- 若已安装 Jekyll：在仓库根目录执行 `bundle exec jekyll serve`（或 `jekyll serve`），浏览器访问 `http://localhost:4000/blog` 查看列表与文章
- 若无本地环境：可直接提交，依赖 GitHub Actions 构建后在线查看

### 4. 提交前自检

- [ ] front matter 中 title、date、tags 正确
- [ ] 正文无敏感信息，占位符为 `******` 或等效
- [ ] 文章在博客列表页可见且点击可进入详情页（本地或部署后验证）
- [ ] 符合 [spec.md](./spec.md) 中 FR-001～FR-005 与 Success Criteria

### 5. 提交与推送

- 将 `_posts/YYYY-MM-DD-speckit-cursor-mac-guide.md` 加入版本控制并提交
- 推送到远端后，GitHub Actions 将构建并部署；在 `https://mr-ma-peng.github.io/blog` 确认文章出现且渲染正确

## 验收

- 列表页：该文章出现在博客列表中，标题与日期正确
- 详情页：正文完整渲染，无敏感信息，结构清晰可读
- 宪章：通过「禁止敏感数据」检查
