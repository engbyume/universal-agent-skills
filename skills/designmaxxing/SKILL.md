---
name: designmaxxing
description: First-pass UI/UX guidance for planning, specifying, reviewing, or changing user-facing design, interactions, usability, or accessibility across websites, apps, games, widgets, and design systems. Load before matching design specialists.
---

# Designmaxxing

Use this skill when a task includes interface design. Apply it as a conditional design guide, not as one visual style or a universal checklist.

## First-pass routing

- Load this baseline after mandatory process skills and before design specialists when a task includes user-facing UI/UX work for a website, app, game, widget, component, prototype, or design system.
- If the same software task includes application-security work, load securitymaxxing in this first pass too. Load both baselines before specialists when both apply.
- After the baseline or baselines, use only matching specialist skills from the active runtime catalog. Specialists add narrower platform, tool, accessibility, or design-system guidance.

## Related specialist skills

- Visual design and design systems: frontend-design, ui-ux-pro-max:design, ui-ux-pro-max:ui-styling, ui-ux-pro-max:design-system, and open-pencil.
- Game interfaces: game-studio:game-ui-frontend.
- Native interfaces: expo:building-native-ui, build-ios-apps:swiftui-ui-patterns, or build-macos-apps:swiftui-patterns.
- Accessibility debugging: a11y-debugging.
- Figma work: use figma:figma-use first, then the matching figma:figma-implement-design, figma:figma-generate-design, or figma:figma-generate-library skill.
- Use only skills available in the active runtime. Do not load the full specialist catalog or treat a skill name as permission to use a plugin or external service.

## Start with the product

- Follow the current request and active project instructions. Identify the product, user, task, content, brand, existing design system, platform, input methods, target sizes, and release context before choosing a direction.
- Distinguish marketing pages, product interfaces, desktop and mobile apps, game menus and HUDs, real-time experiences, inline widgets, dashboards, prototypes, and design systems. Respect host themes and platform conventions.
- For redesigns, inspect the current interface. Preserve its information structure, brand assets, and copy unless the request asks for changes.
- After this baseline, select only references and matching specialist skills from the list above. Do not load every design or media skill.
- Use references/apple-design.md for a mandatory interaction and craft review on every UI task. Apply Apple-specific visual and motion treatments only when they fit the product, platform, user direction, and accessibility needs. Native Apple interfaces must also follow current Apple Human Interface Guidelines and platform APIs.
- Read references/ux-principles.md when a relevant decision could benefit from those prompts or when requested. Treat the concepts as optional heuristics, not universal laws.
- For website work, read references/website-enhancements.md and add only features that solve a real user need.
- For products planned for public release, read references/release-readiness.md when claims, personal data, forms, purchases, tracking, third-party services, or user-generated content are relevant. Apply only the checks that fit the product and target markets. This is not legal advice.
- When implementation security work is in scope, route to the separate securitymaxxing skill. Keep security implementation checklists and tests in that skill.

## Choose a visual direction

- Choose typography, icons, color, density, surface, corner shape, motion, and layout to fit the brief, brand, platform, content, accessibility needs, and existing components.
- Do not impose a default font, icon set, palette, corner style, animation, or design system across products. When design references conflict, follow the current user direction and active project specification.
- Use Dqnamo Kitchen as an optional design-asset reference for selected components, interactions, motion, and visual treatments: [dqnamo.com/kitchen](https://www.dqnamo.com/kitchen). Examples include tactile controls, hold-to-confirm, magnetic drag targets, cassette controls, cards, and loaders. Adapt patterns to the current design system. Check reuse terms before copying code or assets.
- Avoid polished-template defaults. The following are smell tests, not absolute bans. Keep a pattern when it serves the product, brand, content, platform, or user task. Use it minimally when it does not.

1. Harsh gradients: use strong gradients only when they support the brand, depth, or hierarchy.
2. Loose or mismatched icons: keep icon meanings, stroke, size, and optical alignment coherent. A library such as Lucide is fine when it fits.
3. Pure white backgrounds: choose surfaces for the product and reading conditions. Use pure white when it fits.
4. Rainbow coloring: use a limited, purposeful palette unless the information needs more.
5. Drop shadows: use restrained, consistent elevation when it explains depth or interaction.
6. Three feature cards in a row: do not force a three-card marketing template. Let the content determine layout and count.
7. Emojis: avoid them in polished product UI unless the audience or voice calls for them.
8. Liquid glass: do not use it as a default finish. Use it only when the platform and task support it.
9. Em dashes: avoid them in interface copy and follow active writing rules.
10. Inter, Geist, or Space Grotesk defaults: choose typography for the brand, content, and platform rather than habit.
11. Colored left stripes: use them only when they convey a clear semantic or brand role.
12. Fake testimonials: never invent reviews, customer names, quotes, logos, or results.
13. Bento grids: use a grid when the content and task benefit from that structure.
14. Terminal windows: do not add a fake terminal as decoration. Show a real terminal only when relevant and accurate.
15. "It's not X, it's Y" phrasing: avoid this formula in headlines and interface copy.
16. Check-mark bullets: use them for verified completion or meaningful status, not generic decoration.
17. Three pricing tiers: show plans that exist and explain their real differences.
18. No real product demos: when a demo helps explain the product, show a real demo, working example, or accurate product view. Never present a fabrication as real.
19. Soft corner radius: do not round every surface by habit. Match radius to product and platform.
20. Purple and black: do not default to this pairing. Use it when the brand or task supports it.
21. No skeleton loaders: use a skeleton when content shape is known and it improves feedback. Otherwise use another clear loading state.
22. Radial orbs: avoid decorative blobs by default. Use them only when they support the visual direction and do not obscure content.
23. Dot grids: avoid generic background texture. Use them for a deliberate composition.
24. Sparkle icons: reserve them for a product meaning or action that warrants them.
25. Animated rows: animate rows when motion communicates a useful state or change.
26. No terms of service: provide an accurate, working terms link when terms apply or the surface requires it.
27. No privacy policy: provide an accurate, working privacy link when applicable or required.
28. Hover animations: keep them brief and purposeful. Provide equivalent focus and touch feedback and respect reduced motion.
29. Neon colors: avoid them as default accents. Use them for a fitting brand or clear status.
30. Basic pastel colors: choose colors for the product, brand, contrast, and content instead of defaulting to a generic pastel palette.

## Interaction, states, and accessibility

- Design the states the interface needs, including loading, empty, error, success, disabled, focus, destructive, and undo states.
- Check text and non-text contrast, image alternatives, keyboard access, visible focus, clear labels, form errors, appropriate hit targets, zoom and reflow, and reduced motion where relevant.
- Use the current WCAG version as a technical reference for applicable web content. Automated checks alone do not establish accessibility or legal conformance.
- Keep widgets consistent with their host theme and available space. Do not impose an unrelated style.

## Release readiness

Use the conditional checks in references/release-readiness.md when release context calls for them. Verify current official requirements for the target markets and platforms. Do not invent policies, business details, consent, reviews, or claims. A design review cannot guarantee legal compliance or prevent litigation. Refer material legal questions to qualified counsel. This skill does not authorize implementation, use of external assets, publishing, or deployment.
