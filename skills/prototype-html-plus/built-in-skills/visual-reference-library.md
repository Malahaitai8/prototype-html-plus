# Visual Reference Library

Use this file when a high-fidelity prototype needs visual direction beyond the base official design-system route. This library does not provide code to copy. It records reference choices, when to use them, and where the boundaries are.

## Selection Rule

Choose the smallest useful reference set:

1. Product/platform reference: official design system or platform guideline.
2. For iOS or Android Apps, real-product screen and flow references from Mobbin and Page Flows.
3. Style/composition reference: modern UI system or product-surface taste reference.
4. Icon reference: one icon family or platform icon style.
5. Brand asset reference: only when the user confirms logo, mascot, illustration, or imagery needs.

Do not combine references to make the page look busy. Each reference must have a job.

## Official Product And Platform References

| Reference | Use For | Borrow | Do Not Borrow |
| --- | --- | --- | --- |
| Ant Design | B-side admin, CRM, ERP, OA, tables, forms, permissions | Layout, filters, tables, forms, drawers, modals, feedback | Do not import Ant Design or copy component source |
| Carbon Design System | Monitoring, analytics, risk control, industrial, data-dense systems | Metric density, hierarchy, status, readable complex data | Do not turn every B-side screen into a dark command center |
| Fluent 2 | Enterprise collaboration, Microsoft-like tools, calm SaaS | Command bars, collaboration context, restrained surfaces | Do not mimic Microsoft branding or product identity |
| Apple HIG | iOS apps and Apple-like native experiences | Native hierarchy, motion restraint, image and icon clarity | Do not use Apple assets or SF Symbols as copied files |
| Material 3 / Material Web | Android and Material-style apps | Color roles, elevation, motion, component behavior | Do not mix Material with WeUI or Ant Mobile without reason |
| WeUI | WeChat mini programs and WeChat H5 | Cell rhythm, sheets, dialogs, lightweight trust prompts | Do not shrink a B-side admin UI into a phone shell |
| TDesign Mobile | Tencent-style mobile web or Vue mobile products | Mobile component structure and Tencent ecosystem rhythm | Do not use it as a default WeChat mini-program substitute |

Official anchors:

- Ant Design: https://ant.design/docs/spec/introduce/
- Carbon Design System: https://carbondesignsystem.com/
- Fluent 2: https://fluent2.microsoft.design/
- Apple Human Interface Guidelines: https://developer.apple.com/design/human-interface-guidelines/
- Material 3: https://m3.material.io/
- Material Web: https://github.com/material-components/material-web
- Ant Design Mobile: https://mobile.ant.design/
- WeUI: https://github.com/Tencent/weui
- TDesign Mobile Vue: https://tdesign.tencent.com/mobile-vue/overview

## Real-Product App References

Mobbin and Page Flows are research sources, not design systems, code libraries, templates, or asset packs. Use them for Apps only after the platform and current task are confirmed.

| Reference | Use For | Borrow | Do Not Borrow |
| --- | --- | --- | --- |
| Mobbin | Real iOS/Android screen composition, UI elements, page archetypes, density, and visual rhythm | Navigation structure, image ratios, hierarchy, content grouping, action placement, state patterns | Do not copy screenshots, photography, brand names, copywriting, logos, illustrations, or distinctive trade dress |
| Page Flows | Real task sequences, recordings, transitions, and state progression | Step order, entry/exit paths, sheet/modal timing, confirmation and recovery patterns | Do not reproduce a flow blindly when it conflicts with the confirmed PRD or platform guideline |

App reference order:

1. Use Mobbin to select two comparable public samples by platform, business type, page archetype, or UI element.
2. Use Page Flows to validate the current task path when a public flow is available.
3. Resolve conflicts with Apple HIG for iOS or Material 3 for Android.
4. Record sample URLs, extracted rules, anti-copy boundaries, and whether paid content was unavailable.

If login or paid access blocks a source, use public samples and official platform guidance. State the limitation and continue; never claim to have reviewed inaccessible content.

Primary anchors:

- Mobbin mobile: https://mobbin.com/explore/mobile
- Mobbin flows: https://mobbin.com/explore/mobile/flows
- Page Flows: https://pageflows.com/user-flow/

## Modern High-Adoption UI References

These references can improve taste, layout, state detail, and interaction quality, but they are not substitutes for product/platform routing.

| Reference | Heat Signal | Use For | Borrow | Do Not Borrow |
| --- | --- | --- | --- | --- |
| shadcn/ui | Very high GitHub stars/forks; widely adopted in modern SaaS prototypes | Modern SaaS, admin tools, AI products | Composition, spacing, borders, subtle states, command surfaces | Do not copy source, docs prose, or exact component implementations |
| Chakra UI | High GitHub adoption and npm usage | Accessible React-like component thinking | Token discipline, accessible states, pragmatic component APIs | Do not make every page look like a generic component catalog |
| Radix Primitives | High adoption for accessible unstyled primitives | Dialogs, popovers, menus, tabs, switches | Interaction semantics and focus behavior | It is not a visual style or imagery source |
| Headless UI | High adoption for accessible unstyled interaction patterns | Menus, dialogs, transitions, comboboxes | Behavior patterns, keyboard paths, state transitions | It does not solve branding, layout taste, or imagery |
| Magic UI | High GitHub adoption for motion/visual accents | Selected marketing surfaces or polished micro-moments | Restrained motion ideas and memorable detail | Do not use glow, shine, or animated decoration to hide weak layout |

Heat signals must be checked from primary sources before claiming exact current numbers. Prior Step 4 research used GitHub repository stars/forks and package adoption as the gate; future updates should refresh numbers when the exact count matters.

Primary anchors:

- shadcn/ui: https://github.com/shadcn-ui/ui
- Chakra UI: https://github.com/chakra-ui/chakra-ui
- Radix Primitives: https://github.com/radix-ui/primitives
- Headless UI: https://github.com/tailwindlabs/headlessui
- Magic UI: https://github.com/magicuidesign/magicui

## Icon References

High-fidelity prototypes should not use emoji as product icons by default. Pick one icon direction and keep stroke, corner radius, fill, and visual weight consistent.

| Reference | Use For | Borrow | Boundary |
| --- | --- | --- | --- |
| Lucide | Modern SaaS, B-side tools, neutral product UI | 2px line icon feel, simple geometry, clear affordance | Do not import package in V1 demos; use inline SVG/CSS icons when needed |
| Heroicons | Tailwind-like SaaS and clean consumer tools | Solid/outline pairing, navigation and action clarity | Do not mix with unrelated filled icon sets |
| Material Symbols | Android and Material-style products | Platform-recognizable action symbols | Use only for Material route or a confirmed Google-like direction |
| Fluent Icons | Microsoft-style enterprise tools | Rounded enterprise icon rhythm | Use with Fluent-like surfaces, not WeUI mini programs |
| Ant Design Icons | Ant-like admin screens | Admin action vocabulary and status icon patterns | Do not import the icon package or copy exact source |
| SF Symbols | iOS apps | Native iOS icon proportions and semantic system symbols | Do not use Apple asset files; borrow platform logic only |

Icon anchors:

- Lucide: https://github.com/lucide-icons/lucide
- Heroicons: https://github.com/tailwindlabs/heroicons
- Material Symbols: https://fonts.google.com/icons
- Fluent Icons: https://github.com/microsoft/fluentui-system-icons
- Ant Design Icons: https://github.com/ant-design/ant-design-icons
- SF Symbols: https://developer.apple.com/sf-symbols/

## Brand Asset References

Brand assets are optional. Ask whether the user needs them during requirement intake or UI style confirmation. If the user does not need them, skip this route.

Brand assets include:

- Logo: wordmark, lettermark, symbol mark, app icon mark, or combined mark.
- Brand character: mascot, helper, friendly object, abstract guide, or narrative illustration.
- Imagery: real photo, generated image, product still, lifestyle photo, texture, or scene illustration.
- Pictograms and custom icons: product-specific object or category visuals.

Rules:

- Brand assets must be original or user-provided.
- Do not copy existing brand IP, such as a famous mascot, logo, animal character, or campaign image.
- It is fine to borrow the method: "a mascot or visual character creates memory and trust." It is not fine to copy the character.
- Complex mascots, lifestyle scenes, and illustrations require user confirmation before image generation or external image use.
- Network images may be referenced directly when the user allows it, but the source URL must be recorded in the demo or delivery notes.

## Implementation Defaults

- Logo and system icons: prefer inline SVG or CSS shapes in single-file HTML.
- Complex mascot or illustration: confirm first, then use image generation, user-provided assets, or a sourced online image.
- B-side brand assets: usually restrained logo mark and consistent system icons; avoid mascots unless the product is explicitly branded.
- C-side brand assets: logo, character, imagery, and friendly pictograms may be central to trust and memory.
- Emoji icons: disallowed by default for high-fidelity output. Only use emoji if the user explicitly confirms a playful emoji-based style.
