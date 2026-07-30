# Basic High-Fidelity Mode

Use this guide after the user has confirmed a PRD Lite, the current prototype step, platform, design principles, and risk boundaries. High-fidelity mode creates a polished, interactive HTML prototype for visual, interaction, and handoff validation.

高保真必须先确认 UI 风格. Once the user chooses high-fidelity output, do not generate HTML immediately. First produce a UI Style Confirmation sheet, let the user confirm or revise it, then generate the high-fidelity HTML.

High-fidelity has two separable sub-capabilities that are finally merged into the generated prototype:

1. Style system: UI style, layout, typography, color, component density, state expression, and motion rhythm.
2. Brand assets: logo, brand character/mascot, imagery, pictograms, and icon strategy.

Brand assets are optional. Ask whether they are needed during requirement intake or UI style confirmation. If the user does not need them, skip the brand-asset route.

High-fidelity mode can start from either:

- A confirmed PRD Lite with no prior wireframe.
- A confirmed low-fidelity wireframe that the user wants to upgrade.

It must not start from vague requirements, skip UI style confirmation, or implement screenshot rebuild. Region and full screenshot rebuild belong to Step 6.

## Mandatory UI Style Confirmation

High-fidelity has two style routes, but both require confirmation first:

- `basic-hifi`: simple, restrained, official-reference baseline. Use the existing B-side and C-side demos as reference routes when the user confirms "简约基础款 / 规范交付版".
- `styled-hifi`: a user-selected visual direction, such as dark command center, warm lifestyle, premium finance, young social, Apple-like native, Linear-like SaaS, or another confirmed style.

Do not treat `basic-hifi` as a shortcut. It is one selectable style in the UI Style Confirmation sheet.

The style confirmation sheet must use the same status labels as PRD Lite:

- `已确认`: directly stated by the user or already confirmed in the PRD.
- `待确认`: missing and important before visual generation.
- `Agent 假设`: recommended by the Agent and waiting for user approval.

After the user answers, re-output the complete updated UI Style Confirmation sheet and ask for confirmation before generating HTML.

If the user wants logo, brand character, imagery, or custom icons, run the Brand Asset Confirmation sheet before generating or sourcing assets.

If the confirmed platform is iOS or Android, continue with `app-hifi.md` and confirm its App Visual Reference Sheet before generating HTML. UI style confirmation chooses the direction; the App sheet locks real-product samples, task flow, platform behavior, typography, density, and anti-copy boundaries.

## UI Style Confirmation

Use the smallest sheet that matches the product type. Do not ask the same generic visual questions for every product.

### B-side style confirmation

Use for admin, SaaS, dashboard, approval, operations, CRM, ERP, finance, risk control, and internal tools.

```markdown
## UI 风格确认单 - B 端高保真

- 产品类型: [已确认 / 待确认 / Agent 假设]
- 当前 PRD 步骤: [已确认]
- 风格路线: [简约基础款 / Linear-Vercel 式现代 SaaS / 暗色指挥中心 / 企业协作 / 金融风控 / 自定义]
- 官方主参考: [Ant Design / Carbon / Fluent 2 / 组合原因]
- 现代辅参考: [shadcn/ui / Chakra UI / Radix / Headless UI / Magic UI / 不使用]
- 信息密度: [低 / 中 / 高]
- 业务严肃度: [轻量 / 标准 / 严肃 / 高风险]
- 色彩与品牌: [主色、深浅模式、禁用色]
- 排版与空间: [紧凑 / 标准 / 留白更强 / 自定义]
- 图标策略: [Lucide 风格线性图标 / Heroicons 风格 / Fluent Icons 风格 / Ant Design Icons 风格 / 无图标 / 自定义]
- 品牌资产需求: [不需要 / 只需要 logo / logo + 图标 / logo + 品牌形象 / 待确认]
- 配图策略: [无图 / 网上素材 / image-2 生成 / 用户提供 / 待确认]
- 数据可视化强度: [无 / 指标为主 / 图表为主 / 实时监控]
- 操作效率 vs 品牌表现: [效率优先 / 平衡 / 品牌表现优先]
- 状态与风险表达: [成功、警告、异常、处理中、禁用]
- 不使用的风格: [说明哪些官方参考、现代 UI 参考、图标或品牌方向不使用]
```

### C-side mobile style confirmation

Use for consumer apps, mobile H5, mini programs, mobile web, social, commerce, lifestyle, tools, and personal productivity.

```markdown
## UI 风格确认单 - C 端移动高保真

- 产品类型: [已确认 / 待确认 / Agent 假设]
- 当前 PRD 步骤: [已确认]
- 平台: [iOS / Android / H5 / 微信小程序 / 其他]
- 风格路线: [简约基础款 / 温暖生活方式 / 年轻社区 / 高级品牌感 / 自定义]
- 官方主参考: [Apple HIG / Material 3 / Ant Design Mobile / WeUI / TDesign Mobile]
- 现代辅参考: [shadcn/ui / Chakra UI / Radix / Headless UI / Magic UI / 不使用]
- 用户群与情绪: [年龄层、熟悉度、信任需求、情绪基调]
- 品牌气质: [温暖 / 专业 / 年轻 / 高级 / 克制 / 活泼]
- 配图策略: [无图 / 网上素材 / image-2 生成 / 用户提供 / 待确认]
- 图片使用位置: [首屏 / 物品卡 / 空状态 / 引导页 / 说明弹层 / 不使用]
- 是否允许远程图片: [允许 / 不允许 / 待确认]
- 图标策略: [Lucide 风格 / Heroicons 风格 / Material Symbols 风格 / SF Symbols 风格 / 自定义 pictogram / 禁止 emoji]
- 品牌资产需求: [不需要 / logo / logo + 形象 / logo + 形象 + 图标 / 待确认]
- 主色与材质: [主色、背景、卡片/列表/玻璃/纸张等材质倾向]
- 动效需求: [无 / 微动效 / 明显转场 / 状态反馈为主]
- 风险边界表达: [信任、支付、健康、儿童、隐私、社交压力等]
- 不使用的风格: [说明哪些官方参考、现代 UI 参考、图标或品牌方向不使用]
```

### Large-screen style confirmation

Use for command centers, monitoring walls, BI big screens, IoT, city operations, industrial, and security displays.

```markdown
## UI 风格确认单 - 大屏/监控高保真

- 产品类型: [已确认 / 待确认 / Agent 假设]
- 当前 PRD 步骤: [已确认]
- 屏幕与比例: [16:9 / 21:9 / 拼接屏 / 未知]
- 风格路线: [深色指挥中心 / 工业监控 / 金融实时盘 / 简约基础款 / 自定义]
- 官方参考: [Carbon / Ant Design / 其他]
- 明暗模式: [深色 / 浅色 / 双模式]
- 图表密度: [指标 / 趋势 / 地图 / 拓扑 / 表格 / 告警流]
- 告警层级: [普通、关注、严重、恢复]
- 实时状态表达: [刷新频率、在线状态、闪烁/动效限制]
- 可读距离: [近距离操作 / 会议屏 / 远距离展示]
- 不使用的风格: [说明哪些官方参考或视觉方向不使用]
```

### Marketing style confirmation

Use for landing pages, brand displays, product showcases, event pages, portfolios, and other presentation-led prototypes.

```markdown
## UI 风格确认单 - 营销/展示高保真

- 产品类型: [已确认 / 待确认 / Agent 假设]
- 当前 PRD 步骤: [已确认]
- 风格路线: [品牌大片 / 极简高级 / 年轻活动 / 内容杂志 / 自定义]
- 视觉主张: [一句话说明页面气质]
- 首屏重点: [品牌 / 产品 / 场景 / 转化动作]
- 图片/视频/插画: [真实图片 / 生成图片 / 无图 / 用户提供素材]
- 动效需求: [无 / 微动效 / 滚动叙事 / 强转场]
- 转化目标: [预约 / 注册 / 购买 / 留资 / 了解更多]
- 内容密度: [极简 / 标准 / 说明详细]
- 不使用的风格: [说明哪些视觉方向不使用]
```

## Required Reference Declaration

Before generating high-fidelity HTML, state the selected references in the response or working notes:

- Product type: B-side, C-side, or mixed.
- Platform: desktop web, mobile H5, iOS, Android, mini program, large screen, or other.
- Current PRD step being implemented.
- Confirmed style route: `basic-hifi` or `styled-hifi`.
- Confirmed UI style sheet summary.
- Brand asset route: skipped or confirmed.
- Internal references used: `frontend-skill`, `built-in-skills/design-system-reference.md`, `built-in-skills/visual-reference-library.md`, and `built-in-skills/frontend-quality.md`.
- For iOS or Android: `built-in-skills/app-hifi.md`, including the confirmed App Visual Reference Sheet.
- Official reference used and why.
- Modern UI, icon, imagery, and brand references used and why.
- Official references intentionally not used and why.

Do not say "high fidelity" without choosing a reference direction. Do not blend several official systems just to make the page look richer.

## Brand Asset Confirmation

Only use this sheet when the user confirms brand asset needs.

```markdown
## 品牌资产确认单

- 是否需要品牌资产: [已确认 / 待确认 / Agent 假设]
- 品牌名称或产品名: [已确认 / 待确认 / Agent 假设]
- 品牌气质: [温暖 / 专业 / 年轻 / 高级 / 可信 / 活泼 / 克制 / 自定义]
- Logo 类型: [文字标 / 字母标 / 符号标 / 组合标 / App icon / 不需要]
- 品牌形象类型: [不需要 / 吉祥物 / 友好物件 / 抽象助手 / 人物插画 / 场景插画]
- 图标体系: [Lucide / Heroicons / Material Symbols / Fluent Icons / Ant Design Icons / SF Symbols / 自定义]
- 配图来源: [网上素材 / image-2 生成 / 用户提供 / 无图]
- 使用位置: [导航 / 首屏 / 卡片 / 空状态 / 弹层 / 底部导航 / 文档说明]
- 生成方式: [内联 SVG/CSS / 远程图片 / image-2 / 用户素材 / 待确认]
- 禁用相似品牌/IP: [例如不要像美团袋鼠、天猫猫头、京东狗等已有品牌资产]
- 来源记录: [网络素材 URL / 用户提供 / image-2 生成说明]
```

Before generating or sourcing a complex mascot, illustration, or logo, confirm this sheet. Do not invent an existing brand-like character.

## Imagery, Icon, And Brand Asset Rules

- Imagery must serve the product scene, user emotion, or brand trust. Do not add decorative stock photos.
- Default imagery source order: high-quality online material, then image generation, then user-provided assets, unless the user chooses otherwise.
- Remote image URLs are allowed only when the user has confirmed that network-dependent preview is acceptable. Record source URLs.
- High-fidelity output must not use emoji as product icons by default.
- Use inline SVG/CSS for simple logo marks, app marks, system icons, and pictograms in single-file HTML.
- Use image generation, user-provided assets, or sourced online images for complex mascots, lifestyle scenes, or rich illustrations.
- Do not copy existing brand IP, mascot, logo, icon source, or official illustration assets.

## Official Reference Routing

Use `design-system-reference.md` as the routing table. Load only the relevant direction.

Official source anchors:

- Ant Design: https://ant.design/docs/spec/introduce/
- Carbon Design System: https://carbondesignsystem.com/
- Fluent 2: https://fluent2.microsoft.design/
- Apple Human Interface Guidelines: https://developer.apple.com/design/human-interface-guidelines/
- Material Design 3: https://m3.material.io/
- Material Web: https://github.com/material-components/material-web
- Ant Design Mobile: https://mobile.ant.design/
- WeUI: https://github.com/Tencent/weui
- TDesign Mobile Vue: https://tdesign.tencent.com/mobile-vue/overview

### B-Side

- Admin, management, table, form, permission, CRM, ERP, OA, approval: Ant Design.
- Data-dense dashboard, monitoring, risk control, finance, industrial analytics: Carbon plus Ant Design.
- Enterprise SaaS, office collaboration, Microsoft-like tools: Fluent 2.

For Ant Design-like output, emphasize clear workspace structure, navigation, filters, tables, forms, drawers, modals, status feedback, and predictable action placement.

For Carbon-like output, emphasize data density, hierarchy, analytical clarity, operational status, compact metrics, and complex information readability.

For Fluent-like output, emphasize calm surfaces, restrained chrome, collaboration context, stable command bars, and Microsoft-like consistency.

### C-Side

- iOS app: Mobbin public samples for composition, Page Flows for the current task path, and Apple Human Interface Guidelines as the final platform authority.
- Android app or Material style: Mobbin public samples for composition, Page Flows for the current task path, and Material Design 3 / Material Web as the final platform authority.
- Chinese mobile H5: Ant Design Mobile.
- WeChat mini program or WeChat embedded H5: WeUI.
- Tencent-style mobile web or Vue mobile reference: TDesign Mobile Vue.

Do not use a mini-program route as the default for a generic C-side mobile request. Confirm iOS, Android, H5, or mini program first. For App output, follow the typography, safe-area, touch-target, fixed-action, and viewport rules in `app-hifi.md`.

For WeUI-like output, emphasize WeChat ecosystem expectations: simple navigation, cell groups, primary bottom actions, sheet/dialog feedback, lightweight trust prompts, and familiar mini-program interaction rhythm.

## Scope Rule

Only implement the current step from the confirmed PRD step plan.

- Do not create future pages or future steps by default.
- Do not expand a wireframe into a full product unless the current step explicitly requires it.
- If the user asks for screenshot rebuild, explain that it belongs to Step 6 and ask whether they want a from-scratch high-fidelity prototype instead.

## High-Fidelity Requirements

Every high-fidelity HTML prototype must include:

- Previewable single-file HTML.
- No CDN fonts or imported component libraries.
- Remote images only when the user confirmed that network-dependent preview is allowed; record each source URL.
- Realistic product UI, not marketing hero content.
- A visual system aligned to the selected official reference.
- A visual style aligned to the confirmed UI Style Confirmation sheet.
- For iOS or Android, a completed App Visual Reference Sheet aligned to `app-hifi.md`.
- Icon and brand asset choices aligned to the confirmed strategy.
- Complete states for the current step: default, selected, active, empty/loading/error or pending where relevant.
- At least two meaningful interactions, such as filtering, tab switching, detail drawer, modal, sheet, status transition, form feedback, or segmented control.
- Right-side documentation panel.
- Numbered circular pin annotations mapped to documentation items.
- Annotation show/hide control.
- Two-way hover/focus highlighting between pins, UI regions, and documentation items.
- Local preview and verification notes in the delivery message.

## Visual Quality Baseline

Follow `frontend-skill` and `frontend-quality.md`:

- Start with the working surface, not a landing-page hero.
- Use realistic product copy, field labels, statuses, and actions.
- Keep density appropriate to the selected reference.
- Avoid generic dashboard-card mosaics.
- Avoid decorative gradients, stock imagery, fake glassmorphism, and ornamental icons.
- Use one dominant accent unless the selected reference requires more status colors.
- Ensure responsive behavior remains readable on desktop and mobile.

## B-Side Demo Rule

For Step 4 B-side basic demo, use:

- Scenario: data-dense operations monitoring / management console.
- Primary reference: Ant Design for layout, navigation, filters, table, form, drawer/modal, and feedback.
- Secondary reference: Carbon for metric density, operational hierarchy, monitoring status, and complex data readability.
- No Ant Design or Carbon dependency. Borrow principles and component structure only.

## C-Side Demo Rule

For Step 4 C-side basic demo, use:

- Scenario: community idle item exchange WeChat mini program.
- Primary reference: WeUI.
- Do not mix Ant Design Mobile or TDesign unless the user changes the platform to generic H5 or Tencent-style Vue mobile web.
- Avoid making mobile output a shrunken admin console.

## Styled Demo Rule

Step 4 includes two initial styled demos to prove that confirmed UI style changes the output structure, rhythm, material, color, and state expression:

- B-side styled demo: `b-side-modern-saas-ops.html`. Use a Linear/Vercel-like modern SaaS operations console with a restrained logo mark and consistent line icons. It must not look like the basic admin demo with only colors changed.
- C-side styled demo: `c-side-ios-weekend-discovery.html`. Use an original iOS city-weekend discovery product with an editorial image rhythm and a three-screen path from discovery to detail to reservation confirmation. Calibrate with Mobbin public samples, validate the path with Page Flows, and use Apple HIG as the final authority. Do not copy referenced brands, screenshots, copy, photography, or distinctive trade dress.

Future styles can be added later, but do not invent a broad style library in Step 4.

## Delivery Gate

Before delivering:

- Confirm the selected reference is visible in layout, controls, density, states, and interaction behavior.
- Confirm style system and brand asset routes were either confirmed or explicitly skipped.
- Confirm no component-library or font dependency exists.
- Confirm remote image sources are recorded if remote images are used.
- Confirm icon usage is consistent and not emoji-based unless explicitly approved.
- Confirm pins and documentation are still mapped.
- Confirm the current PRD step did not expand silently.
- Tell the user what was built, how to preview/test it, known limits, and ask for acceptance before continuing.
