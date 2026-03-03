# Tasks: Mac 上 Spec-Kit + Cursor 开发需求指南（博客文章）

**Input**: Design documents from `specs/001-speckit-cursor-mac-guide/`  
**Prerequisites**: plan.md, spec.md, research.md, data-model.md, contracts/

**Tests**: Spec 未要求自动化测试；验收为人工（列表可见、正文渲染、无敏感信息）。

**Organization**: Tasks are grouped by user story; single deliverable is one file `_posts/YYYY-MM-DD-speckit-cursor-mac-guide.md`（将 YYYY-MM-DD 替换为实际发布日期）。

## Format: `[ID] [P?] [Story] Description`

- **[P]**: Can run in parallel (different files, no dependencies)
- **[Story]**: User story label (US1, US2, US3) for story phases only
- Include exact file paths in descriptions

## Path Conventions

- **本特性**: 唯一交付物为仓库根目录下 `_posts/YYYY-MM-DD-speckit-cursor-mac-guide.md`
- **规格与契约**: `specs/001-speckit-cursor-mac-guide/` 下 plan.md、spec.md、data-model.md、contracts/post-front-matter.md、quickstart.md

---

## Phase 1: Setup (Shared Infrastructure)

**Purpose**: 确认特性分支与设计文档就绪，无需新建代码结构。

- [x] T001 Verify current branch is `001-speckit-cursor-mac-guide` and design docs exist under `specs/001-speckit-cursor-mac-guide/` (plan.md, spec.md, data-model.md, contracts/post-front-matter.md)

---

## Phase 2: Foundational (Blocking Prerequisites)

**Purpose**: 创建文章文件并写入符合契约的 front matter，使 Jekyll 能识别并在博客列表中展示。

**⚠️ CRITICAL**: 未完成本阶段前，无法进行正文撰写与结构优化。

- [x] T002 Create `_posts/YYYY-MM-DD-speckit-cursor-mac-guide.md` with YAML front matter per `specs/001-speckit-cursor-mac-guide/contracts/post-front-matter.md` (layout: post, title, date, tags); use same date in filename and `date` field

**Checkpoint**: 文章文件已存在且 front matter 正确 → 可开始撰写正文（US1）与结构优化（US3）

---

## Phase 3: User Story 1 - 读者阅读指南 (Priority: P1) 🎯 MVP

**Goal**: 正文完整覆盖 Mac 环境、Spec-Kit、Cursor、开发需求指南四类主题，读者可一次阅读获取完整指南。

**Independent Test**: 从博客列表或直接 URL 打开文章，确认标题与正文完整呈现，且四类主题均有清晰内容。

### Implementation for User Story 1

- [x] T003 [US1] Write article body in `_posts/YYYY-MM-DD-speckit-cursor-mac-guide.md` covering: Mac environment (if any prerequisites), Spec-Kit purpose and usage, Cursor’s role, and development requirements workflow (how to use Spec-Kit + Cursor for spec/requirements), per spec FR-003 and research.md

**Checkpoint**: User Story 1 complete — reader can open and read the full guide with all four topics covered

---

## Phase 4: User Story 2 - 文章发布与可发现 (Priority: P2)

**Goal**: 文章以标准 Jekyll 文章形式存在且能在博客列表中展示，点击可进入详情页。

**Independent Test**: 在博客列表页可见该文章入口；点击后进入详情页且 URL 与站点约定一致。

### Implementation for User Story 2

- [x] T004 [US2] Confirm `_posts/YYYY-MM-DD-speckit-cursor-mac-guide.md` filename and front matter (title, date, tags) match Jekyll convention so the post appears in blog list and detail page; fix if needed

**Checkpoint**: User Story 2 complete — article is discoverable in list and renders on detail page (verify via local `bundle exec jekyll serve` or after deploy)

---

## Phase 5: User Story 3 - 指南结构清晰可跟做 (Priority: P3)

**Goal**: 文章具备清晰层次（引言、二级/三级标题、节间分隔），读者能按步骤跟做。

**Independent Test**: 阅读全文可识别「环境/前置」「主要步骤」「可选或注意」等结构，步骤顺序合理。

### Implementation for User Story 3

- [x] T005 [US3] Add and refine section structure in `_posts/YYYY-MM-DD-speckit-cursor-mac-guide.md`: use `##` and `###` headings, `---` between major sections, per data-model.md and research.md style (align with existing posts e.g. `_posts/2025-06-03-prompt-engineering-thinking.md`)

**Checkpoint**: User Story 3 complete — guide has clear structure and is followable step-by-step

---

## Phase 6: Polish & Cross-Cutting Concerns

**Purpose**: 宪章符合性自检与可选本地验证。

- [x] T006 Self-check `_posts/YYYY-MM-DD-speckit-cursor-mac-guide.md` for constitution compliance: no real tokens, keys, or API keys; any placeholders MUST use `******` or explicit placeholder text (FR-004, constitution I)
- [ ] T007 [P] Optional: Run validation from `specs/001-speckit-cursor-mac-guide/quickstart.md` (e.g. local `bundle exec jekyll serve`, then verify article in blog list and detail page)

---

## Dependencies & Execution Order

### Phase Dependencies

- **Phase 1 (Setup)**: No dependencies — can start immediately
- **Phase 2 (Foundational)**: Depends on Phase 1 — BLOCKS all user story work (T003, T004, T005)
- **Phase 3 (US1)**: Depends on Phase 2 — write body after file and front matter exist
- **Phase 4 (US2)**: Depends on Phase 2; can run in parallel with or after T003/T005 (validation/fix of same file)
- **Phase 5 (US3)**: Depends on Phase 2; can be done together with T003 (same file) or after
- **Phase 6 (Polish)**: Depends on content complete (T003, T005); T006 before commit, T007 optional

### User Story Dependencies

- **US1 (P1)**: After T002; single file — content written in T003
- **US2 (P2)**: Satisfied by T002 + T004 (correct path and front matter)
- **US3 (P3)**: After or combined with T003; structure in T005

### Within This Feature

- T002 creates the only deliverable file; T003, T004, T005, T006 all reference that file
- Recommended order: T001 → T002 → T003 (body) → T005 (structure) → T004 (verify) → T006 (constitution) → T007 (optional)

### Parallel Opportunities

- T007 (optional quickstart validation) is [P] and can run after T006
- T004 and T005 both edit/validate the same file — run sequentially or interleaved; no parallel on same file without conflict

---

## Parallel Example: After Foundation

```bash
# After T002, T003, T005 are done:
# T004: Confirm filename and front matter
# T006: Constitution self-check
# T007 (optional): bundle exec jekyll serve and verify in browser
```

---

## Implementation Strategy

### MVP First (User Story 1 Only)

1. Complete Phase 1: T001
2. Complete Phase 2: T002 (create file with front matter)
3. Complete Phase 3: T003 (write full body covering four topics)
4. **STOP and VALIDATE**: Open article in blog list and detail page; confirm four topics present
5. Deploy or push; confirm live if desired

### Incremental Delivery

1. T001 + T002 → file exists and is listable (US2 partially done)
2. T003 → reader can read full guide (US1 done) → MVP
3. T005 → structure clear (US3 done)
4. T004 → confirm discoverability (US2 done)
5. T006 + T007 → polish and optional validation

### Single-File Workflow

All content tasks (T003, T005, T006) touch the same `_posts/YYYY-MM-DD-speckit-cursor-mac-guide.md`; implement in one branch, commit when constitution check passes.

---

## Notes

- Replace `YYYY-MM-DD` in paths with chosen publish date (e.g. 2025-02-25)
- [P] only where tasks are independent (e.g. T007 vs T006)
- [USn] only in Phase 3–5
- Commit after T006 (and optionally after T003 for incremental history)
