# Frontend Quality Checks

Use this guide before delivering high-fidelity prototypes, wireframes with polished interactions, or screenshot rebuild output.

The goal is to prevent AI-looking product UI: generic layouts, thin states, mismatched references, vague copy, and inaccessible interactions.

## Reference Fit

- State which official reference was selected before generation.
- Check that the page uses that reference's structure and interaction model, not only its colors.
- Do not mix multiple visual systems unless the scenario explicitly calls for it.
- Do not import UI libraries or copy source code from the reference systems in V1.
- If a modern UI, icon, imagery, or brand reference is selected, state what job it performs and what it must not influence.

## App Reference Fit

- For iOS or Android, verify that the App Visual Reference Sheet from `app-hifi.md` was confirmed before HTML generation.
- Use two comparable public Mobbin samples by default and assign each sample a limited job; do not assemble unrelated fashionable screens.
- Use Page Flows to validate the current task sequence when a public flow is available.
- Apple HIG is the final authority for iOS; Material 3 is the final authority for Android.
- If paid or login-only content was inaccessible, disclose the public-sample fallback instead of implying full access.
- Reject output that copies reference branding, copywriting, screenshots, photography, illustrations, or distinctive commercial appearance.

## Product Surface Quality

- Start with the actual work area: navigation, command bar, filters, list/table/feed, detail, status, or primary action.
- Use product copy that an operator or end user would actually see.
- Avoid homepage-style hero text, slogans, empty stats, and generic "AI-powered" claims unless the PRD requires them.
- Every visible section must help the user operate, decide, monitor, browse, reserve, publish, or confirm.

## State Completeness

Include states relevant to the current step:

- Default state.
- Active or selected state.
- Pending, processing, warning, or success state where relevant.
- Empty/loading/error state if the current step depends on data availability.
- Disabled or risky action state when risk boundaries require it.

## Interaction Quality

- Use native buttons, inputs, selects, and focusable controls where possible.
- Every clickable control in the demo should visibly change state or content.
- Modal, drawer, sheet, and detail panel interactions must include an obvious close or back path.
- Hover/focus annotation behavior must not block the core user flow.

## Visual Polish

- Keep typography hierarchy deliberate and compact inside product surfaces.
- Avoid oversized headings in dashboards, admin panels, mobile shells, and documentation panels.
- Use stable dimensions for tables, phone shells, nav items, buttons, status chips, and documentation items.
- Use restrained shadows and borders; do not stack cards inside cards.
- Avoid one-note palettes dominated by a single hue. Use neutral surfaces, one primary accent, and status colors only when meaningful.
- Text must not overflow buttons, chips, tabs, cards, phone screens, or documentation items.

## Mobile Typography And Layout

- Do not use one global web-size value for every mobile text role. Define large title, title, headline, body, subheadline, caption, and Tab Bar label tokens.
- Use a platform system-font stack, an 8-point spacing rhythm, safe-area padding, and at least 44px by 44px touch targets.
- Keep a title separate from badges and actions when horizontal space is limited.
- Clamp supporting descriptions to two lines and ellipsize one-line titles.
- Reserve space for fixed bottom actions, sheets, and Tab Bars so they never cover content.
- Limit pills to real filters or states. Reject decorative pill collections and nested mobile cards.
- Check 393x852, 390x844, and one narrower viewport for overlap, clipping, unexpected wrapping, and hidden controls.

## Confirmed Style Fit

- If the user selected high-fidelity, verify that a UI Style Confirmation sheet was confirmed before HTML generation.
- Verify whether brand assets were needed or explicitly skipped.
- Basic style can be simple and restrained, but it must be explicitly selected or confirmed.
- Styled high-fidelity cannot be only a color swap. It must change enough of the layout, spacing, material, rhythm, status expression, and interaction feel to match the confirmed style.
- Style must not weaken product usability, current-step scope, documentation, numbered pins, or interaction states.
- The generated UI should be able to explain its visual thesis in one sentence, such as "dark command center for live operational triage" or "warm community marketplace for low-pressure neighbor exchange".
- Reject decorative style choices that fight the selected official reference or the product's risk boundaries.

## Imagery, Icon, And Brand Asset Fit

- Imagery must support product context, trust, emotion, or brand memory. It must not be generic decoration.
- Network images are allowed only when confirmed by the user; record source URLs in the demo or delivery notes.
- High-fidelity UI must not use emoji as product icons unless the user explicitly confirmed an emoji style.
- Choose one icon family or icon style direction, then keep stroke, fill, corner radius, and visual weight consistent.
- Logo and system icons should usually be inline SVG/CSS in single-file HTML demos.
- Complex mascots, brand characters, and rich illustrations require user confirmation before image generation or external sourcing.
- Brand assets must be original or user-provided; do not imitate existing brand IP, mascots, or logos.

## Responsive And Accessibility Checks

- Desktop layouts must remain scannable at common laptop widths.
- Mobile layouts must collapse documentation below the prototype or keep the phone shell readable.
- Controls need visible focus states.
- Use semantic landmarks where possible: `main`, `section`, `aside`, `nav`, `button`.
- Do not rely on color alone for status. Pair status color with text labels.

## Anti-Pattern Checklist

Reject output that:

- Looks like a generic card dashboard unrelated to the PRD.
- Skips UI style confirmation after the user chose high-fidelity.
- Claims to be styled but only changes the primary color.
- Uses emoji as product icons without explicit approval.
- Uses a mascot, logo, or brand character that resembles an existing brand IP.
- Adds images or illustrations that do not support the product scene or trust problem.
- Uses B-side tables for C-side mobile flows.
- Uses mobile cards for dense admin workflows that need table/list comparison.
- Mentions reference systems in the UI itself instead of applying them.
- Drops right-side documentation, numbered pins, or local preview notes after visual polish.
- Silently adds future PRD steps.
- Uses unconfirmed remote assets, CDN fonts, imported component libraries, or copied reference code.
- Uses a generic mobile web shell for an iOS or Android App without platform-specific navigation, typography, safe areas, and task states.
