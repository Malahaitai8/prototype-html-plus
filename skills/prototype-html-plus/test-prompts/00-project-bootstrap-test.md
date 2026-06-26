# 测试目标

验证 `prototype-html-plus` Step 0 项目初始化是否完成，并确认后续换电脑可以从 GitHub 文档接续。

# 测试输入

请检查当前仓库的 Step 0 初始化结果，确认项目结构、V1 计划文档、Git 配置和开发记录是否完整。

# 预期行为

Agent 应检查仓库结构和文档，不应开始实现 Step 1 或任何功能能力。

# 预期产物

- 确认根目录存在 `README.md`、`ROADMAP.md`、`PROGRESS.md`、`DECISIONS.md`、`LICENSE`、`.gitignore`。
- 确认存在 `docs/v1-implementation-plan.md`。
- 确认存在 `skills/prototype-html-plus/` 目录骨架。
- 确认 `PROGRESS.md` 记录了 Step 0。
- 确认 Git remote 指向 `https://github.com/Malahaitai8/prototype-html-plus.git`。

# 人工验收点

- `docs/v1-implementation-plan.md` 能让新线程理解 V1 的后续步骤。
- `.gitignore` 没有排除正式项目文档、Skill 文件或测试 Prompt。
- Skill 文件没有把 GitHub 进度记录和测试线程机制描述成最终用户能力。

# 失败表现

- 缺少 V1 接续计划文档。
- 目录结构无法对应说明文档中的 Step 0。
- `PROGRESS.md` 没有记录本次初始化。
- `.gitignore` 误排除了需要提交的正式文件。
- Agent 直接开始实现 Step 1 或后续功能。

