# Reference Skill Analysis

Step 1 目标是把参考仓库和官方设计系统转化为 `prototype-html-plus` 的 V1 设计依据。本文只沉淀可借鉴的结构、流程和设计原则，不复制参考仓库代码。

## 调研结论摘要

- V1 应采用“入口 Skill + built-in skills + starter components + examples”的分层结构，避免把所有规则塞进 `SKILL.md`。
- 原型产物应默认是“左侧可交互 HTML + 右侧说明文档”，并把说明文档作为交付的一部分，而不是装饰栏。
- 所有场景统一使用编号圆点标注，不保留 SVG 长连线方案。
- 线框稿和高保真都同时面向 B 端与 C 端；线框稿强调结构和路径，高保真强调真实产品观感。
- 设计系统参考必须按场景路由加载，不能把所有参考一股脑塞进上下文。
- B 端后台优先参考 Ant Design；数据密集场景参考 Carbon；企业 SaaS / Microsoft 风格参考 Fluent UI。
- C 端 iOS / App 参考 Apple HIG；Android / 跨端 Material 风格参考 Material Design 3；中文移动 H5 / 小程序参考 Ant Design Mobile、WeUI、TDesign Mobile。
- 前端质量规则需要单独沉淀，覆盖 typography、spacing、density、responsive、状态、可访问性和“反 AI 味”。
- 所有参考源只作为概念和方法论参考；不得直接复制代码、样式表、示例页面或文案。

## 社区 Skill / 仓库参考

### vagerent/prototype-html

来源：

- `https://github.com/vagerent/prototype-html`
- 重点：`README.md`、`skills/prototype-html/SKILL.md`、`assets/example.html`

可借鉴点：

- “HTML 原型即说明文档”的交付思路。
- 单文件 HTML 适合快速预览、传递和复测。
- 左侧原型和右侧说明并排，降低产品、前端、业务沟通成本。
- hover 高亮和标注关系能让界面元素与说明项建立对应。

不照搬 / 风险：

- SVG 长连线在复杂页面、表格、看板、移动端页面中容易交叉、偏移或遮挡；V1 不采用。
- 单文件 HTML 可以作为 V1 demo 的优先策略，但不能阻碍后续组件化 starter 的扩展。
- 不复制其 HTML、CSS、图标或示例文案。

落地策略：

- `annotation-doc.md` 继承“原型 + 说明文档绑定”的原则。
- starter demo 可以优先保持单 HTML 可预览。
- 默认采用编号圆点，不提供长连线选项。

### wsdlp46/prototype-html-pin

来源：

- `https://github.com/wsdlp46/prototype-html-pin`
- 计划重点：`SKILL.md`、`README.md`、`assets/annotation-demo.html`

访问状态：

- 本次通过 GitHub 页面和 Git 克隆均未能直接读取该仓库内容。
- 下列结论来自项目说明文档中对该参考源的要求，后续若仓库可访问，应复核。

可借鉴点：

- 用编号圆点替代 SVG 长连线。
- 左侧标注和右侧说明支持双向 hover 高亮。
- 支持标注整体显隐，便于预览时在“干净界面”和“讲解界面”之间切换。

不照搬 / 风险：

- 未直接读取源码前，不得基于它实现具体代码细节。
- 编号圆点也可能遮挡小尺寸控件，需要在 starter 中控制定位、层级和显示密度。

落地策略：

- V1 将编号圆点作为默认标注机制。
- `pin-annotation.js` 未来只实现通用关系绑定，不承载具体业务规则。
- 所有页面统一禁止长连线，避免交付时视觉噪音过高。

### JimLiu/baoyu-design

来源：

- `https://github.com/JimLiu/baoyu-design`
- 重点：`skills/baoyu-design/SKILL.md`、`system-prompt.md`、`references/codex.md`、相关 `built-in-skills/`

可借鉴点：

- 大型 Skill 适合拆成入口、系统提示、references、built-in skills、examples。
- Codex 专用 reference 应写清本地预览、浏览器检查、调试和交付方式。
- 线框稿、高保真、交互原型等能力分层，比一个大提示词更可维护。

不照搬 / 风险：

- 目录结构可以借鉴，但不能直接复制其提示词或内置技能内容。
- `prototype-html-plus` 的定位是产品原型和说明文档，不应泛化成通用设计平台。

落地策略：

- 保持当前 `skills/prototype-html-plus/` 分层目录。
- `SKILL.md` 做入口和路由，具体方法论放到 `built-in-skills/`。
- Step 7 单独写 `references/codex.md`，沉淀本地预览和验证流程。

### agilek/wireframer-skill

来源：

- `https://github.com/agilek/wireframer-skill`
- 重点：`SKILL.md`

可借鉴点：

- 低保真线框稿应服务早期讨论，重点是布局、流程和点击关系。
- 使用真实业务文案，避免 lorem ipsum。
- 可用简单状态控制模拟页面跳转、弹窗、展开收起等交互。
- 手绘感 / Balsamiq 风格适合降低视觉细节争论。

不照搬 / 风险：

- 手绘线框不适合所有 B 端需求；有些团队更需要严肃的结构线框。
- 线框稿不能变成静态图片，V1 仍要求可交互 HTML。

落地策略：

- `wireframe.md` 支持“手绘线框”和“结构线框”两种模式。
- starter 使用真实中文业务内容和可点击状态。
- 线框 demo 不引入复杂视觉装饰。

### qubernetic/wireframe-agent-skill

来源：

- `https://github.com/qubernetic/wireframe-agent-skill`
- 重点：`SKILL.md`

可借鉴点：

- 黑白结构线框适合表达信息层级和空间关系。
- 严格的视觉 token 能避免线框稿越做越像高保真。
- 明确“不可做什么”比只写风格目标更有效。

不照搬 / 风险：

- 过度严格的灰度规则可能限制产品沟通所需的状态表达。
- 等宽字体、虚线、灰阶等只是可选风格，不应成为所有线框稿默认。

落地策略：

- `wireframe.md` 需要定义低保真边界：不做复杂渐变、真实品牌视觉或过度装饰。
- 结构线框使用明确 token，保留少量状态色用于交互可理解性。

### TheGreatGildo/nerv-ui

来源：

- `https://github.com/TheGreatGildo/nerv-ui`
- 重点：`SKILL.md`、组件 demo、CSS tokens

可借鉴点：

- 好的前端 Skill 不只是提示词，还需要 token、组件样式、反模式和示例。
- 视觉规则要具体到字体、颜色、间距、密度、圆角、状态和动效。
- 组件 demo 能帮助验证规则是否真正可落地。

不照搬 / 风险：

- 不直接采用它的视觉风格，避免本项目被另一个 UI 风格吞掉。
- V1 不应过早做完整组件库。

落地策略：

- Step 4 和 Step 5 的 starter components 要具备可复用的 token 结构。
- `frontend-quality.md` 记录反模式和质量检查，而不是只写审美口号。
- demo 用来验证规则，不作为唯一实现模板。

### Leonxlnx/taste-skill

来源：

- `https://github.com/Leonxlnx/taste-skill`
- 重点：`README.md`、`skills/taste-skill/SKILL.md`、`skills/gpt-tasteskill/SKILL.md`、`skills/image-to-code-skill/SKILL.md`、`skills/redesign-skill/SKILL.md`

可借鉴点：

- 先判断页面类型、受众、品牌资产和参考图，再决定设计方向。
- 前端质量需要覆盖 typography、spacing、motion、density、layout variance、responsive、可访问性和状态。
- 图片到代码流程适合局部截图复刻：先分析视觉结构，再实现。
- 已有页面重设计应 audit-first，保留原有风格和功能，只改指定区域。

不照搬 / 风险：

- 该方向包含较多营销站和通用审美判断，本项目应收敛到产品原型、后台系统、数据看板和局部板块复刻。
- 不能把“高级视觉感”误用成过度装饰。

落地策略：

- `frontend-quality.md` 沉淀反 AI 味、真实文案、状态完整性和响应式检查。
- `region-rebuild.md` 采用先分析截图、再确认保留/改动、最后实现的流程。
- 高保真模式默认克制，避免紫蓝渐变、玻璃拟态、模板化卡片堆砌等常见问题。

## 官方设计系统与 C 端参考

### 参考加载路由

使用设计系统参考前，先判断产品场景，只读取最相关的 1-2 个参考，不全量加载：

- 中文 B 端后台 / 管理系统 / 表格表单：优先 Ant Design。
- 数据密集型后台 / 监控 / 风控 / 工业 / 金融分析：Ant Design + Carbon。
- 企业 SaaS / Microsoft 风格 / 办公协作：Fluent UI。
- CRM / ERP / OA / 审批流：Ant Design。
- BI / 指标监控 / 运营分析：Carbon + Ant Design。
- 金融 / 风控 / 交易后台 / 清结算：Carbon 优先，Ant Design 补表单和操作区。
- 内部协作 / 文档 / 日程 / 任务：Fluent UI。
- 工业 / 运维 / IoT 控制台：Carbon 优先，Ant Design 补后台操作控件。
- C 端 iOS App / 类原生 iPhone 体验：Apple HIG。
- C 端 Android App / 跨端 Material 风格 / Google 生态：Material Design 3。
- 中文移动 Web / H5 / 营销活动 / 轻应用：Ant Design Mobile。
- 微信生态 / 小程序 / 微信内 H5：WeUI。
- 腾讯系 C 端或移动 Web / Vue 技术栈参考：TDesign Mobile。

若用户没有说明平台：

- B 端默认走 Ant Design-like 基线。
- C 端默认先追问平台；用户选择“帮我推荐”时，移动 Web / H5 默认参考 Ant Design Mobile，App 默认按 iOS / Android 目标平台选择 Apple HIG 或 Material Design 3。

### Ant Design

来源：

- `https://ant.design/`
- `https://ant.design/docs/spec/introduce`

可借鉴点：

- 适合作为中文 B 端后台、管理系统和中后台产品的默认参考。
- 表格、表单、筛选、弹窗、详情、分页、反馈、空状态等组件体系成熟。
- 风格稳定、密度适中，适合产品和前端沟通。

不照搬 / 风险：

- V1 不引入 Ant Design 组件库依赖，只借鉴视觉语言、组件结构和交互模式。
- 不应把 Ant Design 当成所有场景唯一答案。

落地策略：

- 高保真默认 B 端基线参考 Ant Design。
- `admin-layout.html`、`table-page.html`、`modal.html` 未来应体现类似中后台结构，但使用本项目自有 HTML/CSS。

### Carbon Design System

来源：

- `https://carbondesignsystem.com/`
- `https://github.com/carbon-design-system/carbon`

可借鉴点：

- 适合数据密集型企业系统、数据看板、监控、工业、金融、风控类页面。
- 强调信息层级、数据密度、可访问性和企业级组件一致性。

不照搬 / 风险：

- Carbon 的视觉气质更偏 IBM 企业数据产品，不能直接套到所有中文后台。
- V1 不引入真实 Carbon 依赖。

落地策略：

- 数据看板、复杂表格、指标卡片和分析页可参考 Carbon 的密度控制。
- `dashboard-cards.html` 和 `frontend-quality.md` 应记录数据密集页面的层级和可读性规则。

### Fluent UI

来源：

- `https://fluent2.microsoft.design/`
- `https://github.com/microsoft/fluentui`

可借鉴点：

- 适合企业 SaaS、Microsoft 风格、办公协作和可信赖的内部工具。
- 强调一致性、可访问性、主题 token、多端企业应用体验。

不照搬 / 风险：

- Fluent 的品牌识别较强，只有用户明确需要 Microsoft / Office / 协作工具气质时才应明显参考。
- V1 不引入 Fluent UI 组件库。

落地策略：

- `design-system-reference.md` 未来将 Fluent 作为场景分流选项。
- 高保真页面在办公协作类 brief 中可采用更克制、稳定、浅色的 Fluent-like 视觉基线。

### Apple Human Interface Guidelines

来源：

- `https://developer.apple.com/design/`
- `https://developer.apple.com/design/human-interface-guidelines/`

可借鉴点：

- 适合 iOS / iPadOS / Apple 平台 C 端 App 原型。
- 强调平台一致性、原生导航、手势、系统控件、图标和可访问性。
- Apple 官方设计页明确提供 Human Interface Guidelines、设计资源、SF Symbols 等平台资源。

不照搬 / 风险：

- 不适合默认套到 Android、微信 H5 或普通 Web。
- V1 不导入 Apple 设计资源或图标库，只借鉴平台体验原则。

落地策略：

- 当用户明确要 iOS App、Apple 风格、类原生移动 App 时才读取 Apple HIG。
- C 端线框稿可以借鉴其导航和手势结构，高保真可借鉴 iOS 平台层级和控件感。

### Material Design 3

来源：

- `https://m3.material.io/`
- `https://github.com/material-components/material-web`

可借鉴点：

- 适合 Android App、Material 风格 C 端产品和跨端 Web / App 原型。
- Material Web 说明其基于 Material 3，用于构建美观且可访问的 Web 应用。
- 对色彩、形状、动效、触控目标、表单和状态有完整体系。

不照搬 / 风险：

- Material 视觉识别强，不能默认用于中文 H5、微信生态或 iOS 原型。
- V1 不引入 Material Web 依赖。

落地策略：

- 当用户明确 Android、Google 风格、Material 风格或跨端 App 时再参考。
- 用其触控目标、状态反馈、底部导航、卡片和表单原则指导 C 端原型。

### Ant Design Mobile

来源：

- `https://mobile.ant.design/`
- `https://github.com/ant-design/ant-design-mobile`

可借鉴点：

- 官方定位为构建 mobile web apps 的基础 UI blocks。
- 适合中文 C 端 H5、移动 Web、轻应用和活动型页面。
- 组件强调性能、可定制、原子化能力、手势和细腻动画。

不照搬 / 风险：

- 不等于桌面 Ant Design 的移动缩小版，不能把 B 端表格思维硬塞到 C 端。
- V1 不引入 `antd-mobile` 依赖。

落地策略：

- 当用户提出移动 Web / H5 / 国内 C 端流程时优先参考。
- 高保真 C 端 H5 默认可以参考其组件密度、表单、列表、弹层和反馈模式。

### WeUI

来源：

- `https://weui.io/`
- `https://github.com/Tencent/weui`

可借鉴点：

- WeUI 是微信官方设计团队为微信 Web 开发设计的 UI 框架。
- 包含 button、cell、dialog、progress、toast、article、actionsheet、icon 等移动 Web 常用组件。
- 适合微信生态、小程序、公众号 H5、支付/授权/表单类流程。

不照搬 / 风险：

- 微信生态气质强，不适合作为所有 C 端默认视觉。
- V1 不复制 WeUI 组件代码。

落地策略：

- 当用户明确微信、公众号、小程序、微信内 H5 时参考。
- 用其 cell 列表、toast、dialog、actionsheet、表单和确认反馈模式指导原型。

### TDesign Mobile

来源：

- `https://tdesign.tencent.com/mobile-vue/overview`
- `https://github.com/Tencent/tdesign-mobile-vue`

可借鉴点：

- TDesign Mobile Vue 是面向 Vue 3 和 mobile web application 的 UI component library。
- 支持移动 Web 交互、高质量组件、跨框架一致 API / UI、暗色模式和自定义主题。
- 适合腾讯系、Vue 技术栈、移动 Web 和中性 C 端界面参考。

不照搬 / 风险：

- 技术栈参考不应变成 V1 依赖选择；本项目仍优先生成独立 HTML 原型。
- 不应同时加载 WeUI、Ant Design Mobile、TDesign Mobile，除非用户要求对比方案。

落地策略：

- 当用户明确腾讯系视觉、Vue 移动组件或移动 Web 主题化时参考。
- 用其暗色模式、主题化和跨端一致性作为 C 端高保真补充。

## 对 V1 文件的落地映射

- `SKILL.md`：只做入口、能力路由和约束，不堆叠所有细则。
- `system-prompt.md`：放总方法论和跨模式规则。
- `built-in-skills/requirement-intake.md`：沉淀表单化提问、推荐和跳过初版规则。
- `built-in-skills/wireframe.md`：沉淀手绘线框和结构线框。
- `built-in-skills/hi-fi.md`：沉淀 B 端和 C 端高保真基线。
- `built-in-skills/region-rebuild.md`：沉淀截图分析、保留/改动确认、局部实现边界。
- `built-in-skills/annotation-doc.md`：沉淀右侧说明和编号圆点标注规则。
- `built-in-skills/frontend-quality.md`：沉淀前端质量、反 AI 味、状态、响应式和可访问性检查。
- `built-in-skills/design-system-reference.md`：沉淀 B 端 / C 端设计系统的场景路由，要求只加载相关参考。
- `references/codex.md`：沉淀本地预览、浏览器检查、控制台错误检查和交互验收。

## Step 1 决策

- V1 保持轻量：不引入真实 UI 组件库依赖。
- B 端高保真默认参考 Ant Design；数据密集场景参考 Carbon；企业 SaaS / Microsoft 风格参考 Fluent。
- B 端细分路由：CRM / ERP / OA / 审批走 Ant Design；BI / 监控 / 运营分析走 Carbon + Ant Design；金融 / 风控 / 交易走 Carbon 优先；内部协作走 Fluent；工业 / 运维 / IoT 走 Carbon 优先。
- C 端参考按平台和场景路由：iOS 用 Apple HIG，Android / Material 风格用 Material Design 3，移动 H5 用 Ant Design Mobile，微信生态用 WeUI，腾讯系 / Vue 移动 Web 可参考 TDesign Mobile。
- 默认标注机制只使用编号圆点，不提供长 SVG 连线方案。
- 线框稿和高保真均覆盖 B 端与 C 端；线框稿避免滑向高保真，高保真避免无场景套模板。
- 局部截图复刻必须先确认保留内容和改动内容，不能臆造不可读业务信息。
- 参考仓库只借鉴思路、结构和流程；不复制代码、CSS、示例 HTML 或文案。
