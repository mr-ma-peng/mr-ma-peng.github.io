---
layout: post
title: "在 Mac 上用 Spec-Kit + Cursor 写开发需求与规格指南"
date: 2026-02-25
tags: [Spec-Kit, Cursor, Mac, 需求, 规格, 开发指南]
---

# 在 Mac 上用 Spec-Kit + Cursor 写开发需求与规格指南 🧑‍💻🍎

在使用 Cursor 的过程中，你也许已经发现：让「模型写代码」并不难，真正难的是——**把需求说清楚**、让 AI 按你的意图一步步落地实现。

这个仓库中已经集成了一套基于 Spec-Kit（下文统一记为 **Spec-Kit（speckit）**）的工作流，再配合 Cursor，可以在 **Mac 环境** 下，把「从需求 → 规格 → 计划 → 任务 → 实现」这一整套流程标准化下来。

这篇文章是一份实战向的 **开发需求与规格编写指南**，目标是：在一台 Mac 上，用 Spec-Kit + Cursor 高效完成一个小特性的需求分析与实现准备工作。

---

## 一、准备工作：在 Mac 上的基础环境

在开始之前，建议你在 Mac 上具备以下环境和前置条件：

- 一台安装了 **macOS** 的电脑，终端使用 `zsh` 或 `bash` 均可；
- 已安装并配置好：
  - `git`（用于版本管理，与 GitHub 同步仓库）；
  - Cursor（或兼容的基于 VS Code 的编辑器）；
- 已将本博客仓库（或你自己的项目仓库）克隆到本地；
- 能在终端中执行项目下的 `.specify/scripts/bash/*.sh` 脚本（必要时执行一次权限修复）：

```bash
chmod +x .specify/scripts/bash/*.sh
```

如果你使用的是 GitHub 托管的公开仓库，请务必遵守本项目宪章：**不得提交任何真实的 token、密钥、API Key 等敏感信息**，代码或文档示例中一律使用 `******` 或明确的占位符。

---

## 二、认识 Spec-Kit：用脚本管理「需求生命周期」

Spec-Kit 在这个项目里，通过一组脚本和 Cursor 命令（`/speckit.*`）把「需求生命周期」拆分成几个清晰的阶段：

- **/speckit.specify**：从一句自然语言需求，生成结构化的 `spec.md`；
- **/speckit.plan**：根据规格，生成技术方案与实现计划 `plan.md` 等设计文档；
- **/speckit.tasks**：基于 plan/spec，生成可执行的任务清单 `tasks.md`；
- **/speckit.analyze**：在实现前做一次「规格、计划、任务」的一致性分析；
- **/speckit.implement**：按照 `tasks.md` 的顺序一步步落地实现。

你可以把它理解为：在 Mac 上，本地仓库 + Bash 脚本 + Cursor 组成了一条「需求到实现」的生产线，而你只需要通过命令与聊天，把自己的意图表达清楚，就能复用这条生产线。

---

## 三、在 Cursor 中接入 Spec-Kit 工作流

在 Cursor 中使用 Spec-Kit 的一般方式是：

1. 在项目根目录打开 Cursor；
2. 在 Chat 中输入类似 `/speckit.specify ...` 的命令；
3. 等待脚本与 AI 协作生成相应文档；
4. 查看生成的 `specs/xxx-...` 目录下的文件。

在实际使用时，可以遵循下面几个小技巧：

- **命令尽量用自然语言完整表达需求**  
  例如本次文章的需求输入：
  > 写一篇博客，关于 mac 电脑上，Spec-Kit 使用 Cursor 模型开发需求指南

- **把「上下文约束」直接写在命令里**  
  比如「技术栈使用现有的，风格保持一致」，可以让规划和任务更贴近现有项目。

- **善用已有文档做参考**  
  Cursor 支持直接 `@文件` 或 `@目录` 引用，让模型在修改时参考已有文章风格、配置等。

---

## 四、从需求到规格：/speckit.specify 的使用示例

当你在 Mac 上打开项目后，可以在 Cursor Chat 中输入：

```text
/speckit.specify 写一篇博客，关于 mac 电脑上，Spec-Kit 使用 Cursor 模型开发需求指南
```

这个命令会触发 Spec-Kit：

1. 自动创建一个新的特性分支（例如：`001-speckit-cursor-mac-guide`）；
2. 在 `specs/001-speckit-cursor-mac-guide/` 目录下生成一份 `spec.md`；
3. 规格文件中会包含：
   - 用户故事（User Stories）；
   - 功能需求（FR-001 ~ FR-005）；
   - 可度量的成功标准（SC-001 ~ SC-004）；
   - 边界情况与约束（如 Jekyll 文件命名、敏感信息要求等）。

在这个阶段，你的目标不是写代码，而是**确认「要做什么」被描述清楚**：

- 是否覆盖了所有关键场景？
- 是否有清晰的验收标准？
- 是否遵守了「不得出现真实敏感信息」的宪章要求？

如果有不清楚的地方，可以继续在 Cursor 中和模型对话，修改 `spec.md`，直到规格足够清晰。

---

## 五、从规格到计划：/speckit.plan 如何落到 Mac 项目里

当 `spec.md` 基本定稿之后，在 Cursor 中继续执行：

```text
/speckit.plan  技术栈使用现有的，风格保持一致
```

该命令会：

- 运行 `.specify/scripts/bash/setup-plan.sh`；
- 生成或更新 `plan.md`、`research.md`、`data-model.md`、`quickstart.md` 等设计文档；
- 在计划中写明：
  - 使用的技术栈：本仓库中就是 **Jekyll + GitHub Pages + minimal 主题**；
  - 交付物结构：只需要在 `_posts/` 下新增一篇 Markdown 文章；
  - 宪章检查：明确要求「无敏感信息，示例中使用 `******`」。

在 Mac 上，你只需在 Cursor 中打开这些文件，确认它们是否符合你的预期即可：

- `plan.md`：对整体实现路径是否描述清晰？  
- `data-model.md`：有没有把「文章」当作实体，写清楚 front matter 和正文结构？  
- `quickstart.md`：能否作为你后续操作的「速查手册」？

---

## 六、生成任务清单：/speckit.tasks 帮你拆成可执行步骤

当计划准备好之后，你可以在 Cursor 中执行：

```text
/speckit.tasks
```

这会在 `specs/001-speckit-cursor-mac-guide/` 目录下生成 `tasks.md`，任务会按阶段和用户故事拆分，例如：

- **Phase 1**：确认分支和设计文档存在（T001）；
- **Phase 2**：创建 `_posts/YYYY-MM-DD-speckit-cursor-mac-guide.md` 文件并写好 front matter（T002）；
- **Phase 3（US1）**：撰写覆盖 Mac、Spec-Kit、Cursor、开发需求工作流的正文（T003）；
- **Phase 4（US2）**：确认文章在博客列表和详情页中可见（T004）；
- **Phase 5（US3）**：优化结构与标题层级，让文章可跟做（T005）；
- **Phase 6**：自检是否符合宪章（T006），可选本地预览（T007）。

在 Mac 上，你可以一边在编辑器里修改 `_posts/...md` 文件，一边在 `tasks.md` 中勾选已完成任务，保持实现过程「可跟踪、可回溯」。

---

## 七、按照任务实现：/speckit.implement 与实际写作流程

最后，当你对任务拆分满意时，可以在 Cursor Chat 中输入：

```text
/speckit.implement
```

实现流程大致如下：

1. **完成 T001/T002**：  
   - 确认当前分支为 `001-speckit-cursor-mac-guide`；  
   - 在 `_posts/` 下创建 `2026-02-25-speckit-cursor-mac-guide.md`，并按契约写好 front matter。

2. **完成 T003/T005**：  
   - 先按照 `spec.md` 和 `research.md` 中的要求，写出涵盖四大主题的正文；  
   - 再参照现有文章（如 Prompt 工程、GitHub Pages 教程）的风格，补充二级/三级标题、分割线和列表，让结构更清晰。

3. **完成 T004**：  
   - 检查文件名和 `date` 字段是否一致；  
   - 确认 `layout`, `title`, `tags` 等字段符合站点约定。

4. **完成 T006/T007（可选）**：  
   - 自检是否出现任何真实的 token/密钥/API Key，如需展示则使用 `******`；  
   - 若本地有 Jekyll 环境，可运行 `bundle exec jekyll serve` 在 `http://localhost:4000/blog` 中预览效果。

整个过程，你都可以在 Cursor 里一边聊一边改，让模型帮助你润色文字、拆分小节、检查是否遗漏某个步骤。

---

## 八、敏感信息处理示例：永远只用占位符

由于仓库是公开的，在展示与 AI、CLI 或环境变量相关的配置时，要特别注意「不要把真实密钥写进仓库」。例如：

```bash
export OPENAI_API_KEY=******   # 使用占位符，而不是实际 key
export ANTHROPIC_API_KEY=****** 
```

又比如在配置文件或 README 中：

```yaml
api_key: \"******\"
endpoint: \"https://api.example.com\"
```

只要你保持「**示例里只出现占位符，不出现真实 Secrets**」，就能很好地满足宪章的安全要求。

---

## 九、实战小建议：在 Mac 上让 Cursor 更好帮你

最后，结合 Mac + Spec-Kit + Cursor 的组合，给出几个实践建议：

- **尽量让需求「结构化」**  
  用小标题、列表、编号把你的想法拆开写在命令里，Spec-Kit 与 Cursor 更容易生成清晰的规格与计划。

- **多用「对比现有文件」的方式约束风格**  
  例如你可以对 Cursor 说：「参考 `2025-05-19-github-pages-jekyll-minimal.md` 的写法，帮我重写这一节」，这样能很好地保持站点风格统一。

- **在实现前先跑一遍 /speckit.analyze**  
  对整个 `spec.md`、`plan.md`、`tasks.md` 做一次一致性检查，可以提前发现需求遗漏或命名不一致的问题。

- **提交前做一次「安全与风格双检查」**  
  - 安全：有没有真实密钥、token、域名中带有敏感信息？  
  - 风格：标题层级是否清晰？是否和其他文章一致？是否有明显错别字？

---

## 结语

在 Mac 上使用 Spec-Kit + Cursor，不是「让 AI 替你写全部代码」，而是通过一套可重复的流程，让需求与实现之间的路径更加清晰、可控。

当你习惯了 `/speckit.specify → /speckit.plan → /speckit.tasks → /speckit.analyze → /speckit.implement` 这条链路后，每次新增一个小特性——无论是像本文这样的一篇博客，还是一个小工具——都可以用同样的方式完成，从而把更多时间留给真正重要的思考与创作。

