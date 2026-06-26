# Design System Reference Routing

Use this file only when a prototype request needs visual-system guidance. Do not load every design system reference by default. Choose the smallest relevant reference set based on the user's product type, platform, and audience.

## Routing Rule

Before generating a wireframe, high-fidelity prototype, or region rebuild:

1. Identify whether the target is B-side, C-side, or mixed.
2. Identify the platform: desktop web, mobile web / H5, iOS app, Android app, mini program, large screen, or unknown.
3. Load only the matching reference below.
4. If the platform is unclear and the choice affects the prototype, ask the user or offer a recommended default.

## B-Side References

- Chinese admin / management system / table-form workflows: use Ant Design as the primary reference.
- Data-dense enterprise system / dashboard / monitoring / risk control / finance / industrial analysis: use Ant Design plus Carbon.
- Enterprise SaaS / Microsoft-like / office collaboration: use Fluent UI.
- CRM / ERP / OA / approval workflows: use Ant Design.
- BI / metrics monitoring / operations analytics: use Carbon plus Ant Design.
- Finance / risk control / trading operations: use Carbon for density and hierarchy, with Ant Design for forms and operation areas.
- Internal collaboration / docs / calendar / task management: use Fluent UI.
- Industrial / operations / IoT consoles: use Carbon first, then Ant Design for admin controls.

## C-Side References

- iOS app or Apple-platform experience: use Apple Human Interface Guidelines.
- Android app, Material style, or Google ecosystem: use Material Design 3.
- Chinese mobile web / H5 / lightweight consumer flow: use Ant Design Mobile.
- WeChat ecosystem / mini program / WeChat embedded H5: use WeUI.
- Tencent-style mobile web, Vue mobile component reference, dark mode, or themeable consumer UI: use TDesign Mobile.

## Defaults

- If the user says "后台", "管理系统", "中后台", "表格", or "控制台", default to Ant Design-like B-side guidance.
- If the user says "数据看板", "监控", "风控", or "分析", add Carbon-like density and hierarchy guidance.
- If the user says "企业 SaaS", "协作", "Office", or "Microsoft 风格", use Fluent UI-like restraint.
- If the user says "CRM", "ERP", "OA", "审批", "权限", or "组织架构", default to Ant Design-like admin workflows.
- If the user says "金融", "交易", "风控", "对账", or "清结算", use Carbon-like data density plus Ant Design-like forms and actions.
- If the user says "工业", "运维", "IoT", "设备", or "监控大屏", use Carbon-like hierarchy and operational clarity.
- If the user says "C 端", "移动端", "H5", or "App" but does not specify platform, ask one short platform question before choosing.
- If the user asks you to recommend, use Ant Design Mobile for generic Chinese mobile web / H5, Apple HIG for iOS app, and Material Design 3 for Android app.

## Non-Goals

- Do not import UI libraries in V1 unless a later step explicitly adds that capability.
- Do not merge multiple visual systems into one prototype without a clear reason.
- Do not copy code, CSS, component examples, or prose from the referenced systems.
- Do not use SVG long connector annotations; all prototypes use numbered pin annotations.
