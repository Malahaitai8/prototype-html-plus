# Progress

## 2026-06-26 14:32 - Step 0 Project Bootstrap

### 本次完成
- 初始化 `prototype-html-plus` 项目骨架。
- 沉淀 V1 接续计划到 `docs/v1-implementation-plan.md`。
- 创建根文档、MIT License、`.gitignore` 和 Step 0 测试 Prompt。
- 创建 Skill 目录骨架，保留后续 V1 步骤要填充的位置。

### 当前效果
- 项目已经有可提交的基础结构。
- V1 后续步骤、每步产出和协作规则可以通过文档继续接上。
- 临时草稿、日志、截图和运行产物默认不会进入 Git。

### 测试方式
- 检查目录结构是否存在。
- 检查 `docs/v1-implementation-plan.md` 是否覆盖 Step 0-8。
- 检查 `.gitignore` 是否不会排除正式项目文档、Skill 文件和测试 Prompt。
- 执行 Git 初始化、remote 配置、提交与 push。

### 测试结果
- `rg --files --hidden` 已确认正式文件、Skill 骨架、测试 Prompt 和 `.gitkeep` 均存在。
- `SKILL.md` frontmatter 手工检查通过：包含 `name: prototype-html-plus` 和非空 `description`。
- `quick_validate.py` 因当前 Python 环境缺少 `yaml` 模块无法运行；已记录为环境限制。
- `git check-ignore` 对正式文档、Skill 文件和测试 Prompt 无输出，说明没有被 `.gitignore` 误排除。
- Git 已初始化，当前分支为 `main`。
- GitHub remote 已配置为 `https://github.com/Malahaitai8/prototype-html-plus.git`。

### 遇到的问题 / 瓶颈
- `skill-creator` 初始化脚本第一次运行时，`short_description` 超过 64 字符限制，脚本中途停止；已保留生成的合法目录并手动补齐文件。

### 暂未解决
- Step 1 尚未开始参考仓库调研。
- HTML demo 和本地预览将在后续功能步骤创建。

### 下一步目标
- Step 1：确认参考 Skill 调研范围和输出格式，阅读参考仓库并生成 `docs/reference-skill-analysis.md`。

### Git 提交
- Commit: `chore: bootstrap prototype-html-plus`
- 分支: `main`

## 2026-06-26 15:01 - Step 1 Reference Skill Research

### 本次完成
- 调研并沉淀 `prototype-html-plus` V1 参考体系。
- 新增 `docs/reference-skill-analysis.md`，覆盖社区 Skill / 仓库和官方设计系统。
- 更新 `DECISIONS.md`，记录目录结构、编号圆点、线框分层、高保真基线、设计系统参考和不复制代码原则。
- 新增 `skills/prototype-html-plus/test-prompts/01-reference-analysis-test.md`。
- 确认 `PROGRESS.md` 文件本身是 UTF-8，之前乱码是 PowerShell 显示编码问题。

### 当前效果
- 后续 Step 2-7 有了可接续的参考依据和设计取舍。
- 参考仓库只沉淀为概念、流程和文件映射，没有复制代码。
- 测试 Prompt 可用于新线程单独验证 Step 1 文档质量。

### 测试方式
- 检查 `docs/reference-skill-analysis.md` 是否覆盖全部指定参考源。
- 检查每个参考源是否包含“可借鉴点、不照搬/风险、落地策略”。
- 检查 `DECISIONS.md` 是否记录 Step 1 关键取舍。
- 检查 `01-reference-analysis-test.md` 是否可独立使用。
- 执行 `git diff --check`、`git status --short`。

### 测试结果
- `docs/reference-skill-analysis.md` 已覆盖 10 个参考源：7 个社区 Skill / 仓库方向和 3 个官方设计系统。
- 每个参考源均包含“可借鉴点、不照搬 / 风险、落地策略”。
- `DECISIONS.md` 已记录 Step 1 关键取舍。
- `01-reference-analysis-test.md` 已包含测试目标、测试输入、预期行为、预期产物、人工验收点和失败表现。
- `git diff --check` 通过；仅有 Windows 行尾转换提示，无空白错误。

### 遇到的问题 / 瓶颈
- 通过 Git 克隆 `vagerent/prototype-html` 时，GitHub HTTPS 连接超时；改用浏览器可访问的一手资料和说明文档补充判断。
- `wsdlp46/prototype-html-pin` 本次未能直接访问；已在调研文档中明确标注，未伪装成已读取。

### 暂未解决
- Step 2 需求确认 / 表单化提问能力尚未开始。
- 后续若 `wsdlp46/prototype-html-pin` 可访问，应复核编号圆点实现细节。

### 下一步目标
- Step 2：先确认需求确认表的输出形式、默认轮次、字段范围、推荐/跳过策略和是否沉淀 `requirements.md`，再实现 `built-in-skills/requirement-intake.md`。

### Git 提交
- Commit: `docs: add reference skill analysis`
- 分支: `main`

## 2026-06-26 15:22 - Step 1 Supplemental C-Side References and Scope Convergence

### 本次完成
- 根据用户反馈补充 C 端参考方向。
- 将高保真和线框稿的适用范围明确为同时覆盖 B 端与 C 端。
- 将标注方案收敛为仅使用编号圆点标注，移除长连线方案。
- 新增 `built-in-skills/design-system-reference.md`，用于说明按场景选择参考，避免一次性加载全部设计系统。
- 更新 Step 1 测试 Prompt，增加 C 端参考、场景路由和编号圆点收敛的验收点。
- 根据用户追问补细 B 端场景路由：CRM / ERP / OA、BI / 监控、金融 / 风控、内部协作、工业 / IoT 等分别选择不同参考。

### 当前效果
- Skill 已明确：先判断 B 端 / C 端和平台，再读取对应设计参考。
- C 端参考补充为 Apple HIG、Material Design 3、Ant Design Mobile、WeUI、TDesign Mobile。
- V1 不再保留 SVG 长连线方向。

### 测试方式
- 检查 `docs/reference-skill-analysis.md` 是否包含 C 端参考和场景路由。
- 检查 `skills/prototype-html-plus/built-in-skills/design-system-reference.md` 是否写明按场景选择参考。
- 检查 `SKILL.md` 是否要求不一次性加载所有设计系统。
- 检查 `DECISIONS.md` 是否记录 C 端补充和长连线移除。
- 执行 `rg` 确认不再保留“长连线可选”语义。
- 执行 `git diff --check`、`git status --short`。

### 测试结果
- 已确认 C 端参考包含 Apple Human Interface Guidelines、Material Design 3、Ant Design Mobile、WeUI、TDesign Mobile。
- 已确认 `SKILL.md` 和 `built-in-skills/design-system-reference.md` 写明按场景选择参考，避免一次性加载全部设计系统。
- 已补充 B 端细分路由，避免后台原型一律只参考单一设计系统。
- 已确认当前“长连线”相关表述均为禁止 / 移除语义，不再作为可选方案保留。
- `git diff --check` 通过；仅有 Windows 行尾转换提示，无空白错误。
- 用户已确认可以提交并推送，包含 `PROGRESS.md`。

### 遇到的问题 / 瓶颈
- 上一步未按用户约定在 commit/push 前等待确认；后续改为“产出后先验收，确认后再提交”。

### 暂未解决
- 无。

### 下一步目标
- 进入 Step 2 前先确认需求确认能力的具体规则。

### Git 提交
- Commit: `docs: refine design reference routing`
- 分支: `main`

## 2026-06-26 15:51 - Step 2 Requirement Intake / PRD Lite

### 本次完成
- 新增 `built-in-skills/requirement-intake.md`，定义需求确认 / PRD Lite 工作流。
- 更新 `SKILL.md`，要求模糊需求或信息不足的原型请求先进入 PRD Lite，不直接生成 HTML。
- 更新 `DECISIONS.md`，记录 Step 2 的需求确认规则。
- 新增 `test-prompts/02-requirement-intake-test.md`，覆盖模糊需求、完整 brief、帮我推荐、跳过初版和大范围拆分。
- 根据真实调用测试反馈，补充 PRD 确认闸门、分步执行协议和设计原则确认区。
- 将测试线程生成的 `requirements.md` 加入 `.gitignore`，避免误提交样例 PRD。

### 当前效果
- Skill 能把“表单化提问”落成 Markdown PRD Lite，而不是假设存在真实交互表单。
- 用户已有信息会先被填入 PRD Lite，缺口标记为 `待确认`。
- 推荐内容会标记为 `Agent 假设`。
- 大需求会被拆成主路径初版、扩展交互、异常状态和视觉细化。
- 用户回答追问后必须回显完整更新版 PRD Lite，再确认是否保存和是否进入 Step A。
- 分步计划被定义为执行队列，默认每次只做当前步骤，做完后验收再进入下一步。
- 所有产品类型都必须确认设计原则和风险边界；敏感或情绪化场景需要更仔细，但不是唯一需要确认的类型。

### 测试方式
- 检查 `requirement-intake.md` 是否包含默认流程、PRD Lite 模板、追问规则、推荐/跳过策略、分步规则和保存 `requirements.md` 的边界。
- 检查是否包含 PRD 确认闸门、分步执行协议和设计原则确认区。
- 检查 `SKILL.md` 是否将模糊需求路由到 `requirement-intake.md`。
- 检查 `DECISIONS.md` 是否记录 Step 2 关键规则。
- 检查 `02-requirement-intake-test.md` 是否可独立验证 Step 2。
- 执行关键词覆盖检查和 `git diff --check`。

### 测试结果
- 已确认 Step 2 关键规则均覆盖：PRD Lite、`已确认` / `待确认` / `Agent 假设`、最多 5 个追问、帮我推荐、跳过初版、`requirements.md` 保存边界、原型分步计划、不直接生成 HTML。
- `SKILL.md` 已将模糊需求和信息不足的原型请求路由到 `requirement-intake.md`。
- `02-requirement-intake-test.md` 已覆盖 5 组测试输入。
- `git diff --check` 通过；仅有 Windows 行尾转换提示，无空白错误。
- 本步没有新增 HTML demo，符合“只实现需求确认规则”的范围。
- 已同步到全局 Skill 目录并完成真实调用复测。
- 复测结果：Skill 先输出 PRD Lite，用户回答后回显完整更新版 PRD，没有保存 `requirements.md`，没有生成 HTML，并询问是否确认 PRD、是否保存、是否进入 Step A。

### 遇到的问题 / 瓶颈
- 第一次真实调用时，Skill 在用户回答后直接保存了 `requirements.md`，没有先回显完整 PRD 并等待确认；已通过 PRD 确认闸门修复。

### 暂未解决
- 无。

### 下一步目标
- 进入 Step 3 前先确认线框稿模式的具体规则。

### Git 提交
- Commit: `docs: add requirement intake workflow`
- 分支: `main`

## 2026-06-26 17:18 - Step 3 Generic Wireframe Mode

### 本次完成
- 新增 `skills/prototype-html-plus/built-in-skills/wireframe.md`，定义通用线框稿能力。
- 新增 `skills/prototype-html-plus/starter-components/wireframe-template.html`，提供零外部依赖的单文件 HTML 骨架。
- 新增两个线框示例：
  - `skills/prototype-html-plus/examples/01-wireframe-demo/b-side-data-dashboard.html`
  - `skills/prototype-html-plus/examples/01-wireframe-demo/c-side-ai-fitness-app.html`
- 新增 `skills/prototype-html-plus/test-prompts/03-wireframe-test.md`，用于验证 B 端 / C 端泛化能力。
- 更新 `skills/prototype-html-plus/SKILL.md`，将已确认需求后的低保真线框稿路由到 `wireframe.md`。
- 更新 `DECISIONS.md`，记录 Step 3 关键取舍。
- 根据用户反馈，补充一个全新端到端测试场景：社区闲置交换小程序，从模糊需求挖掘一直测到 Step A 线框稿生成。
- 补充自适应结构规则：线框稿应根据 PRD、平台、领域、信息形态和主行为选择结构，并按场景加载相关设计参考，不应让所有产品长成同一种样式。
- 根据测试反馈，补充移动 / 小程序线框呈现方式规则：支持多屏流程总览和单屏可交互容器；单屏请求不得丢失已确认需求，空间不足时必须建议拆分子步骤。
- 将根目录测试生成的 `*-wireframe.html` 加入 `.gitignore`，避免测试产物误入 Git。
- 根据用户关于长上下文的反馈，补充迭代记忆保护规则：多轮微调后需要回看当前 PRD step、呈现方式、验收目标和 Skill 基线。
- 将真实测试线程生成的 HTML 移到 `test-artifacts/generated-wireframes/`，作为非安装 Skill 的参考产物提交。

### 当前效果
- 线框稿能力被定义为通用能力，不绑定任何固定业务。
- 生成前必须已有已确认 PRD Lite、当前步骤、端型 / 平台、设计原则与风险边界。
- 线框稿默认只做 PRD 分步计划中的当前步骤，完成后等待用户验收。
- 线框稿必须包含右侧说明文档、编号圆点标注、标注显隐、双向 hover / focus 高亮和至少一个基础交互。
- 示例明确写明：demo 仅展示机制和结构差异，不是固定业务模板。
- 测试 Prompt 现在同时覆盖“已确认 PRD 直接生成线框稿”和“全新模糊需求端到端生成线框稿”两类情况。
- 移动线框稿现在要求说明呈现方式，并做当前步骤需求覆盖检查。
- 长时间微调时，Skill 要求 Agent 不只凭上下文记忆继续改，而要在必要时重读当前 HTML / 需求记录并复核基线。
- 测试输出样例被隔离在 `test-artifacts/generated-wireframes/`，不会进入 `skills/prototype-html-plus/` 的安装目录。

### 测试方式
- 本地启动静态服务：
  - `http://127.0.0.1:4311/skills/prototype-html-plus/starter-components/wireframe-template.html`
  - `http://127.0.0.1:4311/skills/prototype-html-plus/examples/01-wireframe-demo/b-side-data-dashboard.html`
  - `http://127.0.0.1:4311/skills/prototype-html-plus/examples/01-wireframe-demo/c-side-ai-fitness-app.html`
- 检查三个 HTML 是否可通过本地 HTTP 加载。
- 检查无外部 CDN / 远程资源依赖。
- 检查右侧说明是否包含原型说明、功能说明、字段说明、交互说明、验收点。
- 检查编号圆点数量、标注显隐、双向 hover / focus 事件钩子。
- 检查 B 端示例是否包含桌面结构线框特征：侧边栏、筛选、表格、详情。
- 检查 C 端示例是否包含移动流程线框特征：手机容器、打卡、状态切换、底部导航、宠物状态。
- 检查测试 Prompt 是否包含全新业务，并明确要求按平台 / 端型 / 参考路由自适应结构。
- 检查单屏移动原型规则是否要求保留上一轮确认需求，不能因屏幕限制丢需求。
- 检查 `.gitignore` 是否忽略根目录测试线框产物。
- 检查长上下文保护规则是否写入 `SKILL.md` 和 `wireframe.md`。
- 检查真实测试 HTML 是否移动到非 Skill 目录，并可被 Git 跟踪。
- 执行 HTML 内联脚本语法检查。
- 执行 `git diff --check`。

### 测试结果
- 三个 HTML 均通过本地 HTTP 加载，返回 200。
- 无外部 CDN / 远程资源依赖。
- 模板包含 5 个编号圆点，B 端 demo 包含 4 个编号圆点，C 端 demo 包含 5 个编号圆点。
- 三个 HTML 均包含说明区标题、标注显隐按钮、`mouseenter` / `mouseleave` / `focusin` / `focusout` 双向高亮钩子。
- B 端 demo 通过桌面结构特征检查。
- C 端 demo 通过移动流程特征检查。
- `03-wireframe-test.md` 已补充社区闲置交换小程序端到端测试，避免只围绕已有两个 demo 验证。
- `wireframe.md` 已补充自适应结构与参考路由规则，避免所有产品输出同一种布局。
- `wireframe.md` 已补充移动呈现方式和需求覆盖规则，避免单屏原型漏掉已确认需求。
- `SKILL.md` 和 `wireframe.md` 已补充长上下文 / 多轮微调保护规则。
- 根目录测试产物已移动到 `test-artifacts/generated-wireframes/`，作为可提交的非安装参考样例。
- `.gitignore` 已改为只忽略根目录临时 `/*-wireframe.html`，不会忽略 `test-artifacts/generated-wireframes/` 下的参考样例。
- 8 个 HTML 均通过本地 HTTP 加载：3 个 Skill template/demo + 5 个真实测试样例。
- 8 个 HTML 内联脚本语法检查通过。
- 已确认 Skill demo 和测试样例中没有本地绝对路径或远程资源依赖模式。
- `git diff --check` 通过；仅有 Windows 行尾转换提示，无空白错误。

### 遇到的问题 / 瓶颈
- 系统 PATH 中没有 `python`，已改用 Codex bundled Python 启动本地静态服务。
- 内置浏览器运行时被沙箱权限挡住，无法完成 in-app browser 自动点击验证。
- 本机 Chrome / Edge headless 在当前环境下没有输出 DOM，也没有生成截图文件；因此本步自动验证以 HTTP 加载、静态结构、事件钩子和脚本语法为主，视觉与点击验收需通过本地 URL 人工确认。

### 暂未解决
- 尚未提交 / 推送，等待用户验收 Step 3 产物。
- 用户确认后，需要在提交前再次检查 `PROGRESS.md`、运行 `git status --short`，再 commit / push。

### 下一步目标
- 用户验收后提交 Step 3。
- 进入 Step 4 前，先确认高保真能力或下一项 V1 能力的具体规则。

### Git 提交
- 待用户确认后提交。

## 2026-06-26 22:18 - Step 4 UI Style Confirmation Enhancement

### 本次完成
- 根据用户反馈调整高保真默认流程：只要用户选择高保真，就必须先输出 UI 风格确认单，确认后才生成 HTML。
- 更新 `built-in-skills/hi-fi.md`，新增 mandatory UI style confirmation、`basic-hifi` / `styled-hifi` 路由、四类动态确认单：B 端、C 端移动、大屏 / 监控、营销 / 展示。
- 更新 `built-in-skills/frontend-quality.md`，增加风格确认后的质量检查：风格化不能只换主色，必须改变布局、空间、材质、节奏、状态表达，同时不能牺牲可用性和标注文档。
- 更新 `SKILL.md`，明确高保真请求必须先确认 UI 风格。
- 更新 `test-prompts/04-hi-fi-test.md`，加入风格确认单测试和两个风格化高保真场景。
- 新增两个风格化 demo：
  - `examples/02-hi-fi-demo/b-side-dark-command-center.html`
  - `examples/02-hi-fi-demo/c-side-warm-lifestyle-exchange.html`
- 保留原有两个基础款 demo，作为风格确认单里“简约基础款 / 规范交付版”的参考路线。
- 更新 `DECISIONS.md` 和 `docs/v1-implementation-plan.md`，记录 UI 风格确认是 Step 4 的强制闸门。

### 当前效果
- 高保真不再允许“确认 PRD 后直接生成 HTML”；必须先确认 UI 风格。
- 基础款、深色指挥中心、温暖生活方式成为 Step 4 初始风格参考，后续可继续扩展风格库。
- B 端风格化 demo 改为深色数据指挥中心，强调高密度监控、态势图、告警流和异常处理队列。
- C 端风格化 demo 改为温暖生活方式社区交换，强调生活场景、品牌化头部、故事卡片、温和预约和风险边界。

### 测试方式
- 先执行 RED 探针，确认强制 UI 风格确认规则和两个风格化 demo 在修改前缺失。
- GREEN 后检查 `hi-fi.md` 是否包含强制 UI 风格确认、四类动态确认单、`basic-hifi` / `styled-hifi` 路由。
- 检查四个 demo 是否都存在，且风格化 demo 包含右侧说明文档、编号标注、标注显隐、双向 hover / focus 和至少两个交互。
- 检查风格化 demo 无外部 CDN / 远程资源依赖。
- 执行 HTML 内联脚本语法检查、临时 HTTP 预览探针和 `git diff --check`。

### 测试结果
- RED 探针按预期失败，确认强制 UI 风格确认规则和两个风格化 demo 在修改前缺失。
- GREEN 探针通过，确认 `hi-fi.md` 已包含强制 UI 风格确认、四类动态确认单和两个风格化 demo 文件。
- 综合静态检查通过，确认风格路由关键词、质量检查、四个 demo 的标注机制、交互钩子、无外部依赖和内联脚本语法均通过。
- 临时 HTTP 预览探针通过，四个 demo 均返回 200，并在响应中包含右侧说明文档结构。

### 遇到的问题 / 瓶颈
- 无新的阻塞问题；继续沿用 PowerShell 静态检查 + 临时 Node 脚本验证方式，避免 `node -e` 多层引号不稳定。

### 暂未解决
- 暂未建立完整风格库；本次只先沉淀基础款、深色指挥中心、温暖生活方式三个初始参考方向。

### 下一步目标
- 验证 Step 4 UI 风格确认增强后，根据用户验收决定是否继续泛化更多风格示例。

### Git 提交
- 待用户确认后提交。

## 2026-06-26 21:56 - Step 4 Basic High-Fidelity Mode

### 本次完成
- 新增 `built-in-skills/hi-fi.md`，定义 Basic High-Fidelity Mode 的输入边界、官方参考声明、场景路由、当前步骤约束和交付闸门。
- 新增 `built-in-skills/frontend-quality.md`，沉淀高保真前端质量检查：参考贴合、真实产品表面、状态完整性、交互、视觉、响应式和可访问性。
- 新增两个 starter shell：`starter-components/hi-fi-admin-shell.html` 和 `starter-components/hi-fi-mobile-shell.html`。
- 新增两个完整高保真 demo：`examples/02-hi-fi-demo/b-side-operations-console.html` 和 `examples/02-hi-fi-demo/c-side-community-exchange-wechat.html`。
- 更新 `SKILL.md`，将已确认需求后的高保真请求路由到 `hi-fi.md`，并明确截图重建属于 Step 6。
- 新增 `test-prompts/04-hi-fi-test.md`，覆盖 B 端 Ant Design + Carbon 和 C 端 WeUI 两个高保真场景。
- 更新 `DECISIONS.md`、`ROADMAP.md`、`README.md` 和 `docs/v1-implementation-plan.md`，同步 Step 4 不再只是后台 admin，而是 B/C 双 demo 的基础高保真模式。

### 当前效果
- 高保真生成前必须声明产品类型、平台、当前 PRD 步骤、选用官方参考、选用原因和不使用的参考。
- Step 4 支持从确认 PRD 直接生成高保真，也支持从已确认线框升级到高保真。
- B 端 demo 主参考 Ant Design，辅参考 Carbon；用于后台布局、筛选、表格、状态、抽屉、弹窗、指标密度和监控层级。
- C 端 demo 主参考 WeUI；用于微信小程序导航、可信身份提示、物品列表单元、底部主操作、发布弹层和 toast 反馈。
- Step 4 明确不做截图局部重建或完整截图复刻。

### 测试方式
- 执行 Step 4 文件存在性探针。
- 检查 `hi-fi.md` 是否包含内部 Skill、官方参考源、参考声明规则和 Step 6 边界。
- 检查两个 demo 是否无外部 CDN / 远程资源依赖。
- 检查两个 demo 是否包含右侧说明文档、编号圆点标注、标注显隐、双向 hover / focus 高亮和至少两个真实交互。
- 检查 B 端 demo 是否体现 Ant Design + Carbon 的官方参考路线。
- 检查 C 端 demo 是否体现 WeUI / 微信小程序路线，而不是后台缩小版。
- 执行 HTML 内联脚本语法检查。
- 执行 `git diff --check`。

### 测试结果
- Step 4 文件存在性探针通过，确认 `hi-fi.md`、`frontend-quality.md`、双 demo 和 `04-hi-fi-test.md` 均已创建。
- 静态 Step 4 检查通过，确认官方参考关键词、Step 6 边界、标注机制、右侧说明文档、关键交互钩子和 HTML 内联脚本语法均通过。
- `git diff --check` 通过；仅出现 Windows 行尾转换提示，无空白错误。

### 遇到的问题 / 瓶颈
- `node -e` 在当前 PowerShell 环境下多层引号传递不稳定；已改用 PowerShell 原生静态检查，并将内联脚本临时写入系统临时目录用 `node --check` 验证。

### 暂未解决
- Step 5 annotation-doc 独立能力尚未开始；当前 Step 4 demo 内仍内置说明文档和编号标注机制。
- Step 6 screenshot rebuild 尚未开始；截图相关请求仅在 Step 4 中明确边界。

### 下一步目标
- 验证 Step 4 产物后，根据用户验收决定是否提交 / 推送。
- 进入 Step 5 前，先确认侧边文档和编号标注是否要抽成独立 starter 组件与脚本。

### Git 提交
- 待用户确认后提交。

## 2026-06-26 23:18 - Step 4 Style System And Brand Asset Enhancement

### 本次完成
- 根据用户反馈，将 Step 4 高保真拆成两个可独立路由、最终合并的子能力：风格系统与品牌资产。
- 新增 `skills/prototype-html-plus/built-in-skills/visual-reference-library.md`，记录官方设计系统、高热度现代 UI、图标体系和品牌资产参考边界。
- 更新 `SKILL.md`，写入“新步骤 / 新子功能 / 范围重定义前至少两轮问题，每轮不少于两个问题”的协作门禁。
- 更新 `built-in-skills/requirement-intake.md`，在 PRD Lite 里增加高保真视觉与品牌资产需求入口。
- 更新 `built-in-skills/hi-fi.md`，增加 UI 风格、视觉参考、配图策略、图标策略、品牌资产确认单和品牌资产生成边界。
- 更新 `built-in-skills/frontend-quality.md`，增加配图、图标、logo、品牌形象和禁止默认 emoji 图标的质量检查。
- 新增两个增强版风格 demo：
  - `examples/02-hi-fi-demo/b-side-modern-saas-ops.html`
  - `examples/02-hi-fi-demo/c-side-branded-lifestyle-exchange.html`
- 将 `test-prompts/04-hi-fi-test.md` 收敛为用户要求的两句真实测试提示词。

### 当前效果
- 高保真不再只确认 UI 风格，还会确认视觉参考、图标策略和是否需要品牌资产。
- 品牌资产不是强制能力；用户不需要 logo / 形象 / 配图 / 图标策略时会明确跳过。
- B 端增强 demo 走 Linear/Vercel 式现代 SaaS，使用克制 logo mark 和内联 SVG 线性图标。
- C 端增强 demo 根据用户反馈覆盖为鲜生即时到家业务，借鉴美团买菜类产品的信息结构、商品流和购买路径，但使用原创品牌“巷鲜达”、原创蔬果配送形象、统一线性图标、远程商品配图和来源记录。

### 测试方式
- 使用 `04-hi-fi-test.md` 中的 B 端 / C 端两句提示词做人工验收。
- 静态检查规则、demo 文件、内联脚本语法、远程图片来源记录和 `git diff --check`。

### 测试结果
- 关键词覆盖检查通过，确认协作门禁、视觉参考库、品牌资产、图标策略、禁用默认 emoji 和两句测试提示词均已写入。
- HTML 结构检查通过，两个增强版 demo 均包含右侧说明文档、编号标注、标注显隐、双向 hover / focus 和交互钩子。
- 两个增强版 demo 的内联脚本均通过 `node --check`。
- 临时 HTTP 预览探针通过，两个增强版 demo 均返回 200，并包含右侧说明文档结构。
- 新增增强版 demo 通过 emoji 检查，未使用 emoji 作为产品图标。
- `git diff --check` 通过；仅有 Windows 行尾转换提示，无空白错误。

### 追加调整
- 用户指出 C 端社区交换 demo 排版混乱且品牌理念不应像标签一样堆在首页。
- 已按用户确认覆盖当前 C 端品牌 demo 为鲜生即时到家高保真，不新增第三个 C 端 demo。
- 新 demo 默认采用“定位 / 配送时效 + 搜索 + 优惠 + 分类横滑 + 商品流 + 悬浮购物车 + 底部导航”的购买路径。

### 遇到的问题 / 瓶颈
- Windows 环境下 `apply_patch` 删除旧 untracked HTML / prompt 文件失败；已改为新增增强版 demo，并用 PowerShell 覆盖测试提示词文件。

### 暂未解决
- 旧风格化 demo 仍保留为历史初始验证稿，增强版 demo 才是当前 Step 4 风格系统与品牌资产参考。

### 下一步目标
- 完成静态检查和用户验收后，再决定是否提交 / 推送。

### Git 提交
- 待用户确认后提交。

## 2026-06-28 - Step 4 App High-Fidelity And Template Enhancement

### 本次完成
- 新增 `built-in-skills/app-hifi.md`，建立 App 视觉参考单、Mobbin / Page Flows 使用边界、iOS / Android 路由、移动排版契约和交付闸门。
- 更新 `SKILL.md`、`hi-fi.md`、`visual-reference-library.md` 和 `frontend-quality.md`，将 iOS App 路由锁定为“Mobbin 公开样本 + Page Flows 任务流 + Apple HIG”，Android 保留 Material 3 路由。
- 重做 `starter-components/hi-fi-mobile-shell.html`，形成原生 shell、发现流、详情页、底部 Sheet 和确认态组成的 iOS 模板套件。
- 新增规范化 C 端 demo `examples/02-hi-fi-demo/c-side-ios-weekend-discovery.html`，产品为原创城市周末发现 App“周末里”。
- C 端 demo 覆盖发现首页、活动详情和预约确认三屏路径，包含筛选、详情进入 / 返回、收藏、场次选择、确认反馈和标注双向高亮。
- 旧 `c-side-branded-lifestyle-exchange.html` 已移除；Skill 和文档统一引用新文件名。
- 更新 `04-hi-fi-test.md` 的 C 端提示词为 iOS 城市周末生活发现 App。

### 当前效果
- App 高保真不能只声明 Apple HIG 或 Material 3；必须先说明真实产品样本、任务流、借鉴点和明确不复制内容。
- Mobbin / Page Flows 登录或付费内容不可访问时，允许使用公开样本与官方规范继续，但必须披露访问范围。
- iOS 模板和 demo 使用独立的大标题、标题、正文、辅助信息、说明文字和 Tab 标签字号，不再用网页式全局 `14px` 处理移动端文字。
- demo 使用系统字体、8pt 节奏、44px 触控区、safe area、两行说明限制和固定操作预留空间。
- 标注默认隐藏，右侧文档可控制显隐；产品首屏不会被编号圆点破坏。

### 测试结果
- 规则覆盖检查通过：App 视觉参考单、Mobbin / Page Flows、Apple HIG / Material 3 路由、公开样本回退、反复制边界和移动排版门槛均已写入。
- starter 与 demo 均包含 7 个编号标注、标注显隐、双向 hover / focus、发现页、详情页、Sheet 和成功态；内联脚本通过 `node --check`。
- 系统 Chrome 桌面截图确认远程图片正常加载，App 和右侧文档无文字重叠或异常换行。
- 精确浏览器复测通过：393×852、390×844、360×780 均无横向溢出，手机容器与视口尺寸一致。
- 三屏交互复测通过：详情打开、Sheet 关闭、成功态和“周日 19:30”场次回写均正确。
- `git diff --check` 通过；仅有 Windows 行尾转换提示。

### 遇到的问题 / 瓶颈
- Playwright CLI 无法直接启动用户目录 Chrome，返回 `spawn UNKNOWN`；改用系统 Chrome + Playwright Core CDP 完成同等精确视口和交互验收。

### Git 提交
- 待用户验收后提交。
