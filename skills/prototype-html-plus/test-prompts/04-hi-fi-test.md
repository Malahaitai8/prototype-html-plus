# Step 4 High-Fidelity Test Prompts

Use these two prompts to manually inspect whether `prototype-html-plus` now asks for style/reference/asset confirmation before generating high-fidelity output, and whether the final prototype looks good enough.

## B-side prompt

```text
我想生成一个 B 端高保真产品原型：AI 运营控制台，用来监控多渠道客服会话、识别高风险工单、分配人工跟进。请先按 prototype-html-plus 的规则确认 UI 风格、视觉参考和图标策略，再生成当前 Step A 的高保真 HTML。
```

## C-side prompt

```text
我想生成一个 C 端 iOS 高保真产品原型：城市周末生活发现 App，用户可以浏览精选地点和活动、查看详情、收藏并完成预约确认。请先按 prototype-html-plus 的规则确认 UI 风格、App 视觉参考单、Mobbin 公开样本、Page Flows 任务流、配图和图标策略，再生成当前 Step A 的三屏高保真 HTML。
```
