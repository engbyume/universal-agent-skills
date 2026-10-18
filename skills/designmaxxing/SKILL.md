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
- When a user directly authorizes a build, treat design concepts and specialist reviews as internal quality checks. Do not require a second approval before reversible local implementation. Pause only for a user-requested review, an unresolved material choice, or a genuine authority boundary. Keep account access, paid use, consent, external publication, production changes, and destructive actions gated.

## Related specialist skills

- Visual design and design systems: frontend-design, ui-ux-pro-max:design, ui-ux-pro-max:ui-styling, ui-ux-pro-max:design-system, and open-pencil.
- Game interfaces: game-studio:game-ui-frontend.
- Native interfaces: expo:building-native-ui, build-ios-apps:swiftui-ui-patterns, or build-macos-apps:swiftui-patterns.
- Accessibility debugging: a11y-debugging.
- Figma work: use figma:figma-use first, then the matching figma:figma-implement-design, figma:figma-generate-design, or figma:figma-generate-library skill.
- System architecture, when relevant: load platform-architecture for backend boundaries, distributed systems, data consistency, messaging, scaling, deployment, observability, or recovery decisions that affect the product. Keep the design review focused on user-facing experience.
- Use only skills available in the active runtime. Do not load the full specialist catalog or treat a skill name as permission to use a plugin or external service.

## Start with the product

- Follow the current request and active project instructions. Identify the product, user, task, content, brand, existing design system, platform, input methods, target sizes, and release context before choosing a direction.
- For a new public website or app, begin with a short goal check before recommending accounts or integrations. Capture its main outcome, target users, launch audience or markets, existing tools and data, and business model. If the prompt already gives this information, summarize it instead of repeating questions. Ask only for missing goals that change the product or service recommendation.
- Use those goals to recommend relevant services and accounts, such as cloud hosting, a CRM, identity, payments, analytics, or email. Explain each recommendation and any likely cost or sign-in need. Tell the user before the first provider sign-in. Never request passwords, tokens, or API keys in chat, and do not create accounts or incur paid charges without authorization.
- When the user asks to build or edit a product, change the active project or named app builder directly and verify the result there. Do not stop at a concept mockup or create a parallel prototype when implementation was requested. A mockup may guide the implementation.
- Use one current supported implementation path. Do not add fallback code or backward-compatibility layers for hypothetical old clients or versions. Preserve real user data, security properties, and verified external contracts.
- When a user-facing feature needs live data, use push subscriptions or another real-time delivery method instead of polling. Load platform-architecture for the transport and provider choice.
- Distinguish marketing pages, product interfaces, desktop and mobile apps, game menus and HUDs, real-time experiences, inline widgets, dashboards, prototypes, and design systems. Respect host themes and platform conventions.
- For redesigns, inspect the current interface. Preserve its information structure, brand assets, and copy unless the request asks for changes.
- After this baseline, select only references and matching specialist skills from the list above. Do not load every design or media skill.
- Use references/apple-design.md for a mandatory interaction and craft review on every UI task. Apply Apple-specific visual and motion treatments only when they fit the product, platform, user direction, and accessibility needs. Native Apple interfaces must also follow current Apple Human Interface Guidelines and platform APIs.
- Read references/ux-principles.md when a relevant decision could benefit from those prompts or when requested. Treat the concepts as optional heuristics, not universal laws.
- For any website, read references/website-enhancements.md. Complete its public launch baseline before release; treat the enhancement ideas as conditional.
- For products planned for public release, read references/release-readiness.md when claims, personal data, forms, purchases, tracking, third-party services, or user-generated content are relevant. Apply only the checks that fit the product and target markets. This is not legal advice.
- For substantial design reviews, new journeys, or cross-platform experiences, read references/design-review-checklist.md and apply only the sections that fit. For small targeted edits, use only matching prompts. The checklist does not replace user research or accessibility testing.
- When implementation security work is in scope, route to the separate securitymaxxing skill. Keep security implementation checklists and tests in that skill.

## Choose a visual direction

- Choose typography, icons, color, density, surface, corner shape, motion, and layout to fit the brief, brand, platform, content, accessibility needs, and existing components.
- Do not impose a default font, icon set, palette, corner style, animation, or design system across products. When design references conflict, follow the current user direction and active project specification.
- For every new website, app, game, or major UI direction, read [references/design-asset-sources.md](references/design-asset-sources.md). It lists the approved asset sources, the no-generated-production-assets rule, and the required research-before-mockup workflow.
- When web implementation or hosting choices are part of the design task, read references/stack-preferences.md. Apply those defaults only to new or unconstrained web work; preserve existing stacks and native or game platform requirements.
- Do not generate or hand-create production design assets such as logos, illustrations, photos, icon sets, textures, decorative graphics, sprites, or 3D art. Reuse current project or user-provided assets, or source licensed assets from the approved set. You may implement layouts and ordinary UI components in code. A concept mockup is allowed when it is clearly labeled and grounded in research; do not ship its placeholder or generated artwork as an asset. A later explicit user request can override this restriction.
- Before settling on a new direction or major journey, review at least two relevant products, websites, component examples, or mockups where available. Record their URLs and the patterns you plan to adapt. Public browsing may be used for design research, but sites outside the approved asset list are reference-only and do not become asset sources. Recreate useful patterns in a distinct direction; do not copy complete screens, branding, or signature artwork.
- Aim for polished, premium execution that feels unique to this product, audience, and platform. Do not reuse one visual template across different products by habit.
- Avoid polished-template defaults. The following are smell tests, not absolute bans. Keep a pattern when it serves the product, brand, content, platform, or user task. Use it minimally when it does not.

1. Harsh gradients: use strong gradients only when they support the brand, depth, or hierarchy.
2. Loose or mismatched icons: keep icon meanings, stroke, size, and optical alignment coherent. Reuse existing project or platform icon sets. For new icon assets, follow the approved source list. Do not draw or generate a new icon family.
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

## UI primitives and design systems

- For a new React web interface using shadcn/ui, always use the companion shadcn-ui-design-system skill to establish design tokens and components in the active project. Its pinned source is [shadcn-ui/ui at d2fba50](https://github.com/shadcn-ui/ui/tree/d2fba50ee5b9113008b5bb908563527b7efd2f27/skills/shadcn). If the active runtime cannot load the companion, follow the universal skill-intake audit for that pinned source before activating it. The companion uses Base UI primitives by default for new projects.
- Treat shadcn-ui-design-system as the authority for shadcn setup, the pinned CLI, and autonomy defaults. Load another shadcn guide only for component-specific details it adds, and follow the pinned companion when instructions conflict.
- For an existing shadcn project, inspect and extend its current design system. Keep its configured primitive base unless the user requests a migration. Add only components required by the product.
- For native apps and games, use the platform's own accessible primitives and the matching specialist skill instead of forcing React components into the project.
- For component patterns and approved source limits, follow [references/design-asset-sources.md](references/design-asset-sources.md).

## Interaction, states, and accessibility

- Design the states the interface needs, including loading, empty, error, success, disabled, focus, destructive, and undo states.
- Check text and non-text contrast, image alternatives, keyboard access, visible focus, clear labels, form errors, appropriate hit targets, zoom and reflow, and reduced motion where relevant.
- Use the current WCAG version as a technical reference for applicable web content. Automated checks alone do not establish accessibility or legal conformance.
- Keep widgets consistent with their host theme and available space. Do not impose an unrelated style.

## Release readiness

Use the conditional checks in references/release-readiness.md when release context calls for them. Verify current official requirements for the target markets and platforms. Do not invent policies, business details, consent, reviews, or claims. A design review cannot guarantee legal compliance or prevent litigation. Refer material legal questions to qualified counsel. A direct user request authorizes the requested reversible implementation in the active project. This skill does not grant reuse rights to external assets or authorize paid services, account creation, publication, or production deployment.
