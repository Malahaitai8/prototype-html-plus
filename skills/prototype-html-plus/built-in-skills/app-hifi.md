# App High-Fidelity Reference And Template Rules

Use this guide whenever the confirmed high-fidelity platform is iOS or Android. It complements `hi-fi.md`; it does not replace PRD Lite, UI style confirmation, brand-asset confirmation, or the current-step boundary.

App high-fidelity must not be generated from platform guidelines alone. Platform guidelines define correct behavior, while real-product references calibrate composition, content density, typography rhythm, image treatment, and task flow.

## Reference Stack

Use the smallest reference stack that covers the work:

1. Real-product screen reference: Mobbin public mobile screens, UI elements, and flows.
2. Task-flow reference: Page Flows public recordings or annotated flows.
3. Platform authority: Apple Human Interface Guidelines for iOS, or Material Design 3 for Android.
4. Product-specific imagery and brand assets: only after the user confirms the asset route.

Do not treat Mobbin or Page Flows as code libraries, component packages, or assets that can be copied. They are research sources. Do not copy product names, copywriting, screenshots, photography, logos, distinctive trade dress, or proprietary illustrations.

If paid or login-only content cannot be accessed, use public samples and the selected official platform guideline. State that paid content was not reviewed; do not imply otherwise and do not block generation.

## Mandatory App Visual Reference Sheet

Complete and confirm this sheet after the UI Style Confirmation sheet and before generating App HTML.

```markdown
## App 视觉参考单

- 产品类型: [已确认 / 待确认 / Agent 假设]
- 平台: [iOS / Android]
- 当前 PRD 步骤: [已确认]
- 核心任务: [用户在本步骤要完成的单一主任务]
- 页面原型: [发现流 / 内容流 / 搜索 / 详情 / 交易 / 预约 / 账户 / 工具 / 其他]
- Mobbin 检索词: [业务词 + 页面词 + UI element / flow 词]
- 公开样本 1: [产品 / 页面类型 / URL / 借鉴点]
- 公开样本 2: [产品 / 页面类型 / URL / 借鉴点]
- 公开样本 3: [可选；只在确有第三种结构价值时使用]
- Page Flows 任务流: [流程名称 / URL / 关键步骤]
- 平台规范: [Apple HIG / Material 3]
- 导航与返回: [Tab Bar / Navigation Bar / back / modal / sheet]
- 排版层级: [大标题、标题、正文、辅助信息、标签]
- 媒体策略: [图片比例、裁切、文字是否覆盖图片]
- 内容密度: [低 / 中 / 高，以及每屏核心信息数量]
- 主操作位置: [底部固定 / 导航栏 / 内容内 / sheet]
- 必备状态: [默认、选中、加载、空、错误、成功、禁用]
- 明确不复制: [品牌、文案、图片、特色造型、商业外观]
- 访问说明: [公开内容已查看 / 付费内容未查看并已回退]
```

Reference selection rules:

- Use two public samples by default. Add a third only when it contributes a different page archetype or state.
- Select samples from the same platform and a comparable task. Do not borrow iOS navigation for Android or vice versa.
- Give each sample one or two jobs. For example: one sample for discovery composition, one for detail hierarchy, and Page Flows for the transition path.
- Extract rules, not pixels. Recreate the product's own information hierarchy and brand expression.

## Platform Routing

### iOS

- Real-product calibration: Mobbin mobile screens and flows.
- Task path: Page Flows iOS examples when available.
- Authority: Apple Human Interface Guidelines.
- Use system-font behavior, safe-area spacing, clear navigation hierarchy, restrained materials, native-feeling sheets, and a stable Tab Bar.
- Use inline SVG icons with SF Symbols-like semantic clarity, but do not copy or redistribute Apple symbol assets.

### Android

- Real-product calibration: Mobbin Android screens and flows.
- Task path: Page Flows Android examples when available.
- Authority: Material Design 3.
- Use Material color roles, navigation patterns, elevation, sheets, motion, and state behavior.
- Use Material Symbols-like semantics without importing remote font or icon packages in a single-file prototype.

### Mini Program And Mobile Web

Do not route mini programs or H5 through this App guide by default:

- WeChat mini program / WeChat H5: WeUI.
- Chinese mobile H5: Ant Design Mobile.
- Tencent-style Vue mobile web: TDesign Mobile.

Mini-program references are not the default for generic C-side mobile requests. Confirm the platform first.

## Mobile Typography And Layout Contract

Use a platform-appropriate system font stack. Do not import a CDN font and do not use one global web-size value for all text.

Recommended iOS prototype tokens:

| Role | Size / Line height | Use |
| --- | --- | --- |
| Large title | `28px / 34px` | Top-level destination or editorial lead |
| Title | `22px / 28px` | Screen or detail title |
| Headline | `17px / 22px` | Row title, section heading, primary action |
| Body | `17px / 24px` | Primary reading and descriptions |
| Subheadline | `15px / 20px` | Metadata and supporting information |
| Caption | `13px / 18px` | Timestamps, tertiary labels, compact notes |
| Tab label | `10px / 12px` | Tab Bar labels only |

Layout rules:

- Base spacing follows an 8-point rhythm, with 4-point half-steps only for icon/text alignment.
- Main horizontal content inset is usually 20px; compact rows may use 16px after visual review.
- Interactive controls need at least a 44px by 44px hit area.
- Respect top and bottom safe areas inside the phone viewport.
- Do not scale font size with viewport width.
- Keep one dominant text hierarchy per region. Do not place title, badge, metadata, and action in one crowded row.
- One-line titles use ellipsis. Supporting descriptions use at most two lines with line clamping.
- A chip or badge must add state or filtering value. Do not use pills as decoration or as a substitute for hierarchy.
- Avoid nested cards. Prefer full-width sections, media blocks, lists, and dividers.
- Fixed bottom actions and Tab Bars must reserve content space and never cover text or controls.

## Composable App Template Kit

The mobile starter must demonstrate these four composable patterns in one dependency-free HTML file:

1. Native App shell: status area, safe areas, navigation bar, Tab Bar, and page transitions.
2. Discovery feed: one strong image-led lead, concise sections, horizontal editorial items, and a readable vertical list.
3. Detail page: immersive media, back/favorite actions, title and metadata hierarchy, readable content, and one fixed primary action.
4. Sheet and confirmation state: native-feeling bottom sheet, selected state, close path, submit feedback, and success confirmation.

The kit is structural. Replace business copy, brand, imagery, and current-step states from the confirmed PRD and App Visual Reference Sheet.

## App Delivery Gate

Before delivery:

- Confirm the App Visual Reference Sheet is complete and present in the documentation or delivery notes.
- Check 393x852, 390x844, and one narrower mobile viewport.
- Confirm no text overlaps, unexpected wrapping, clipped controls, or content hidden behind fixed UI.
- Confirm discovery, detail, back, sheet, selection, submit, and close paths work where relevant to the current step.
- Confirm annotation pins are hidden by default for styled App demos and remain available through an explicit toggle.
- Confirm network image source URLs are recorded when remote imagery is used.
- Confirm the result does not copy a referenced product's branding or distinctive assets.

## Source Anchors

- Mobbin mobile: https://mobbin.com/explore/mobile
- Mobbin mobile flows: https://mobbin.com/explore/mobile/flows
- Page Flows: https://pageflows.com/user-flow/
- Apple Human Interface Guidelines: https://developer.apple.com/design/human-interface-guidelines/
- Material Design 3: https://m3.material.io/
