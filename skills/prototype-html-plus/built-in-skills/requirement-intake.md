# Requirement Intake

Use this guide when the user gives a vague product idea, asks to make a prototype without enough detail, or asks for help clarifying a prototype request. The output is a Markdown PRD Lite that can constrain later HTML prototype work.

Do not generate HTML during requirement intake. First produce or update the PRD Lite, ask only the blocking questions, and get confirmation before moving to wireframe, high-fidelity, or region rebuild work.

## Default Workflow

1. Read the user's initial request and extract all known facts.
2. Create a PRD Lite draft using the template below.
3. Mark every important item as one of:
   - `已确认`: stated by the user.
   - `待确认`: missing or unclear and important to the prototype.
   - `Agent 假设`: recommended by Codex or inferred from context.
4. If core information is missing, ask at most 5 blocking questions in one round.
5. If the user says "帮我推荐", fill recommendations as `Agent 假设` and ask for confirmation.
6. If the user says "跳过，直接生成初版", do not jump straight to HTML. Generate a PRD Lite draft with assumptions, then ask the user to confirm whether to continue.
7. When the user answers clarification questions, update and re-output the complete PRD Lite. Do not skip directly to saving files or generating HTML.
8. Before prototype generation, run the PRD confirmation gate below.
9. If working in a project workspace, suggest saving the confirmed PRD Lite as `requirements.md`, but ask before writing the file.

## PRD Confirmation Gate

After the user answers the intake questions, always show the updated complete PRD Lite and ask for explicit confirmation.

Use this confirmation block:

```markdown
请确认这版 PRD Lite：

1. PRD 内容是否通过？如果不通过，请指出要改的部分。
2. 是否保存为 `requirements.md`？未确认前我不会写文件。
3. 下一步是否只进入 `Step A 主路径初版`？未确认前我不会生成 HTML。
```

Hard rules:

- Do not generate HTML before the user confirms the updated PRD Lite.
- Do not write `requirements.md` before the user explicitly confirms saving.
- Do not treat "按推荐继续" as permission to generate HTML. It only confirms assumptions unless the user also confirms entering the next prototype step.
- If the user asks "先生成 PRD，不用做 HTML", output or update the PRD only. Do not save it unless the user also asks to save it.
- If the user confirms saving but not prototype generation, save the PRD if allowed, then stop and ask what to do next.

## When To Ask Questions

Ask questions only for blocking information. If the missing detail is not critical, make a clearly labeled `Agent 假设` and keep moving.

Must ask when any of these are missing or contradictory:

- Target side and platform: B-side / C-side, desktop web / mobile web / H5 / iOS / Android / mini program / large screen.
- Prototype goal: what the page or module needs to communicate or validate.
- Primary user role and core task.
- Output mode: wireframe, high-fidelity, or wireframe first then high-fidelity.
- Scope: page, module, flow, or region to prototype.
- Core modules or information blocks.
- Key data, fields, states, or business boundary needed to make the prototype realistic.

Do not ask more than 5 questions per round. Prioritize questions that determine scope, platform, output mode, core modules, and data/fields.

## PRD Lite Template

Use this structure by default. Keep it concise, but complete enough to guide the next prototype step.

```markdown
# 原型 PRD Lite

## 1. 需求状态
- 当前阶段：需求确认 / PRD 草案 / 已确认可进入原型
- 完整度判断：可进入原型 / 需要补充后再进入原型
- 阻塞问题数量：

## 2. 原型目标与使用场景
- 目标：
- 使用场景：
- 期望沟通对象：产品 / 业务 / 前端 / 领导 / 用户测试
- 状态：已确认 / 待确认 / Agent 假设

## 3. 端型、平台与设计参考路由
- 端型：B 端 / C 端 / 混合 / 待确认
- 平台：桌面 Web / 移动 Web / H5 / iOS / Android / 小程序 / 大屏 / 待确认
- 推荐参考：
- 路由理由：
- 状态：已确认 / 待确认 / Agent 假设

## 4. 用户角色与核心任务
- 主要用户：
- 核心任务：
- 使用频率 / 场景压力：
- 状态：已确认 / 待确认 / Agent 假设

## 5. 输出模式
- 模式：线框稿 / 高保真 / 先线框稿后高保真
- 原因：
- 状态：已确认 / 待确认 / Agent 假设

## 6. 页面 / 模块范围
- 本次要做：
- 本次不做：
- 后续可扩展：
- 状态：已确认 / 待确认 / Agent 假设

## 7. 核心模块
- 模块 1：
- 模块 2：
- 模块 3：
- 状态：已确认 / 待确认 / Agent 假设

## 8. 数据、字段与状态
- 核心数据：
- 关键字段：
- 关键状态：正常 / 加载 / 空 / 错误 / 禁用 / 成功 / 失败 / 其他
- 状态：已确认 / 待确认 / Agent 假设

## 9. 关键交互与反馈
- 筛选 / 搜索：
- Tab / 切换：
- 弹窗 / 抽屉 / 详情：
- 展开收起 / 批量操作 / 状态切换：
- 状态：已确认 / 待确认 / Agent 假设

## 10. 右侧说明文档要求
- 原型说明：
- 功能说明：
- 字段说明：
- 交互说明：
- 改动说明：
- 验收点：
- 状态：已确认 / 待确认 / Agent 假设

## 11. 编号圆点标注重点
- 标注 1：
- 标注 2：
- 标注 3：
- 标注 4：
- 状态：已确认 / 待确认 / Agent 假设

## 12. 验收点
- 验收点 1：
- 验收点 2：
- 验收点 3：
- 状态：已确认 / 待确认 / Agent 假设

## 13. 设计原则与边界
- 情绪基调：
- 激励 / 惩罚边界：
- 视觉方向：
- 用户心理注意点：
- 明确不做的反模式：
- 状态：已确认 / 待确认 / Agent 假设

## 14. 原型分步计划
- Step A 主路径初版：
- Step B 扩展交互：
- Step C 异常状态 / 空状态 / 加载状态：
- Step D 视觉细化 / 高保真补充：
- 当前建议先做：

## 15. 分步执行协议
- 默认每次只执行：
- 当前步骤完成后的验收方式：
- 用户验收后如何调整计划：
- 状态：已确认 / 待确认 / Agent 假设

## 16. 需要用户确认的问题
1.
2.
3.
```

## Question Format

Use Markdown questions that the user can reply to directly. Prefer compact multiple-choice plus a free-text fallback.

Example:

```markdown
我先把已知信息整理成 PRD Lite。还有 4 个问题会影响原型方向：

1. 这个原型主要面向哪类端型？
   - A. B 端后台 / 管理系统
   - B. C 端移动 Web / H5
   - C. C 端 App
   - D. 其他：____

2. 你希望先做哪种输出？
   - A. 线框稿
   - B. 高保真
   - C. 先线框稿，确认后再高保真

3. 本次原型优先覆盖哪个范围？
   - A. 一个核心页面
   - B. 一个局部模块
   - C. 一个主流程
   - D. 其他：____

4. 有无参考截图、现有系统或风格要求？
   - A. 有，我会上传 / 描述
   - B. 没有，请帮我推荐
```

## Help-Me-Recommend Behavior

When the user asks for recommendations:

- Pick the smallest reasonable set of assumptions.
- Mark every recommendation as `Agent 假设`.
- Explain why the recommendation fits.
- Ask the user to confirm or adjust before generation.

Common defaults:

- Vague B-side admin: Ant Design-like reference, wireframe first if scope is not stable.
- Data dashboard / monitoring / analytics: Carbon-like hierarchy plus Ant Design-like controls.
- Generic Chinese mobile H5: Ant Design Mobile reference.
- iOS app: Apple HIG.
- Android app: Material Design 3.
- WeChat mini program / embedded H5: WeUI.

## Skip-To-Draft Behavior

If the user says "跳过，直接生成初版":

- Do not generate HTML immediately.
- Produce a PRD Lite draft from available information.
- Fill missing non-blocking items as `Agent 假设`.
- List remaining risks.
- Ask: "如果这个 PRD 草案可以接受，我下一步再生成原型。"

If core information is still too vague to create even a draft, ask up to 5 blocking questions.

## Scope Splitting Rule

Large requests must be split. Do not ask Codex to generate a complete complex product in one step.

Default split:

1. 主路径初版: one core page, module, or flow that proves the product idea.
2. 扩展交互: filters, tabs, modals, drawers, batch actions, secondary states.
3. 异常状态: loading, empty, error, permission, disabled, success/failure feedback.
4. 视觉细化: high-fidelity polish after structure and scope are accepted.

Always name the recommended first slice in `原型分步计划`.

## Step Execution Protocol

The prototype step plan is an execution queue, not a decorative note.

Default rule:

- Execute only the current step, usually `Step A 主路径初版`.
- Do not implement Step B/C/D in the same generation unless the user explicitly expands the current scope.
- After each step, show the user what was produced, how to preview/test it, known issues, and the next recommended adjustment.
- Wait for user acceptance or revision before moving to the next step.
- If user feedback changes the scope, update the PRD Lite and step queue before continuing.

Each completed prototype step must end with:

```markdown
## 本步验收
- 本步完成：
- 如何预览 / 测试：
- 已知问题：
- 建议调整：
- 下一步建议：

请确认：本步是否通过？是否调整 PRD 或进入下一步？
```

## Design Principle Confirmation

For every product type, explicitly confirm design principles and risk boundaries before prototype generation. This applies to B-side, C-side, desktop, mobile, internal tools, dashboards, forms, consumer apps, and local modules.

Sensitive or emotion-heavy domains such as health, finance, children, education, gamification, social, AI decision support, and penalty/reward systems require extra care, but they are not the only cases that need this confirmation.

Include:

- Emotional tone.
- Incentive and penalty boundary.
- Visual direction.
- User psychology concerns.
- Anti-patterns to avoid.
- Business / operational risk boundary.
- What the prototype must not imply, promise, or overstate.

Example:

```markdown
设计原则待确认：
- 宠物机制是陪伴监督，不是羞辱惩罚。
- 惩罚必须有挽回路径，避免用户中断后直接流失。
- 文案要接住低行动力用户，避免指责。
```

For B-side examples, confirm principles such as operational efficiency, information density, permission visibility, auditability, error recovery, and whether the interface should feel conservative, data-heavy, or guidance-oriented.

## Saving Requirements

If the user is working in a repo or project folder, suggest saving the confirmed PRD Lite as `requirements.md`.

Do not write `requirements.md` unless the user confirms. If saved, keep it as project planning material, not a Skill runtime capability.
