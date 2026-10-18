# Design asset sources and reference research

Use this reference whenever agents choose visual assets or design a new UI direction. It separates approved asset sourcing from broader visual research.

## Approved asset sources

The approved source set consists of user-provided project assets, an existing user-curated asset collection when its contents are available in the current task, and the curated sources below. Do not add another asset marketplace or source without explicit user approval.

| Source | Use | Reuse boundary |
| --- | --- | --- |
| [Minimal Gallery](https://minimal.gallery/) | Website examples, templates, and tools. Use it to find relevant website patterns and licensed offerings. | A listed website, screenshot, template, or tool is not automatically reusable. Check the specific asset's terms. |
| [Kage](https://kage.design/) | Real product pages, component examples, styles, and mockups. | Kage states that screenshots belong to their respective products and are shown for inspiration and commentary. Treat them as references unless the owner grants reuse rights. |
| [Appshot Gallery](https://www.appshot.gallery/) | Mobile product pages, App Store screenshot sequences, and icon examples. | Use screenshots and icons to study hierarchy and storytelling. Do not republish them as product assets without permission or a license. |
| [Component Gallery](https://component.gallery/) | Components and design-system examples. Use it to compare structure, behavior, and variants. | A component example is a pattern reference. Import code or graphics only when the source provides clear reuse terms. |
| [Dqnamo Kitchen](https://www.dqnamo.com/kitchen) | Previously approved reference for interactive components, tactile controls, and motion patterns. | Adapt interaction ideas to the product. Check terms before copying any code or asset. |
| Existing user-curated collection | Assets already saved by the user and made available in the current project context. | Treat these as user-provided assets. Do not guess collection contents or claim access when they are unavailable. |

## Approved component primitives

- Use the official [shadcn/ui](https://ui.shadcn.com/) component system and registry for React projects that fit the user's web stack. Set up or extend the design system in the active project with the companion shadcn skill.
- Use [Base UI](https://base-ui.com/react/overview) as the default accessible primitive layer for new React/shadcn projects. It is a component primitive library, not a general asset marketplace.
- Keep component-gallery websites as pattern references. Add component code only from the official shadcn registry, Base UI, an existing approved project source, or a source the user explicitly names.
- Do not add an unapproved component registry to broaden the asset set.

## Asset creation rule

- Do not generate or hand-draw production illustrations, logos, photos, icon families, textures, decorative imagery, sprites, or 3D artwork. This includes using image-generation tools for finished assets.
- You may write layout, CSS, and ordinary interface components. Reuse existing project assets and platform-native UI elements where they fit.
- If a required production asset is missing from the approved set, use a non-decorative layout or platform primitive, or ask the user to provide an asset or approve another source. Do not invent a new asset.
- A curated gallery is not a reuse license. Check the original asset's provenance, license, attribution, and commercial-use limits before importing it.
- A clear, current user request can override this rule for a specific asset.

## Research before design

- For every new app, site, game, or major UI direction, inspect at least two relevant products, websites, components, or mockups when available. Use the four new galleries as quick discovery sources. If they do not provide enough examples, public web research may find comparable products for reference only.
- Record the reference URLs, the relevant interaction or visual pattern, and how the design will adapt it to the current audience, brand, platform, content, accessibility needs, and design system.
- Recreate the useful interaction or information pattern, not the complete screen, product identity, logo, or signature artwork. A reference is evidence for design decisions, not permission to copy.
- If the brief lacks visual direction, research comparable work before making a mockup. An original mockup is allowed as a clearly labeled concept. Use placeholders or approved assets, and do not present the mockup as a functioning product demo or ship it as production artwork.
- Aim for polished, premium craft and a distinctive result for each product. Premium describes the quality of execution, not one universal visual style. Do not recycle a template across unrelated products.

Research-source snapshot: 2026-10-12.
