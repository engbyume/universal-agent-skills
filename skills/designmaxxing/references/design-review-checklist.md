# Expanded design review checklist

## Scope and use

Use this reference for substantial design reviews, new user journeys, cross-platform interfaces, game or spatial interfaces, and AI interactions. It expands the designmaxxing baseline. It does not replace the Apple craft review, UX-principle notes, optional website features, or release-readiness checks. Read the sections that fit the product. A checklist does not prove usability or accessibility.

For each applied check, connect the decision to a user task and a way to evaluate it. Mark irrelevant sections with a short reason when recording a full review.

## 1. User needs and evidence

- State the user's main task and the observable outcome the interface should support.
- Record assumptions separately from evidence. Identify which uncertain assumptions could change the design.
- Describe the context of use, including device, environment, time pressure, interruptions, connectivity, and support needs.
- Learn from actual or likely users, including disabled people and people who need assistance when they are part of the audience.
- Prototype high-risk or unfamiliar interactions early, at the fidelity needed to answer the question.
- Evaluate task completion, errors, recovery, and user understanding. Do not rely on preference votes alone.
- Revisit user needs as the service changes. Do not claim research occurred unless it did.

## 2. Contextual interaction principles

Use these as an optional review lens, not as new universal UX laws. ISO 9241-110 describes interaction principles whose priority depends on the task, user, environment, and consequences.

- Suitability for the task: remove work that does not help complete the user's goal.
- Self-descriptiveness: make the current state, available actions, and next step understandable.
- Conformity with expectations: follow familiar language and platform patterns unless evidence supports a change.
- Learnability: let people discover and understand new interactions without memorizing hidden gestures.
- Controllability: support stopping, going back, canceling, or undoing where the action permits it; allow useful individualization.
- Use error robustness: prevent avoidable mistakes, explain errors, preserve recoverable input, and support repair.
- User engagement: consider satisfaction and motivation without manipulating users or adding pressure.

When principles conflict, use the task, risks, accessibility, and observed user behavior to decide. Cite a principle as a question, not as proof.

## 3. Information structure and content

- Organize the information around user tasks, decisions, and vocabulary rather than internal team structure.
- Make navigation labels specific enough that users can predict the destination.
- Put required information before the decision that depends on it. Keep optional explanation available without hiding important terms.
- Use headings, lists, labels, and meaningful link text to support scanning and assistive navigation.
- Keep labels consistent across the journey. Explain unfamiliar domain terms where they first affect a decision.
- Include entry points, prerequisites, handoffs, completion, and support in end-to-end journey maps.
- Check long, translated, missing, and user-generated content so the layout still communicates the same relationships.

## 4. Semantics and custom interactions

- Prefer native platform controls when they meet the need. For a custom control, define its accessible name, role, value, and state.
- Keep visual order, reading order, and keyboard focus order aligned with the task.
- For custom composite widgets, follow the relevant platform keyboard model. Do not add ARIA roles without implementing their expected keyboard behavior.
- For dialogs, define the accessible name, initial focus, keyboard navigation, Escape behavior, and where focus returns. Mark a dialog modal only when users cannot interact with the background.
- Announce important dynamic status changes without moving focus unexpectedly.
- Provide text or structured alternatives for charts and diagrams when their relationships or values matter to a task.

## 5. Web accessibility details

For web content, review the current WCAG target that applies. This is a design checklist, not a conformance claim.

- Check reflow at narrow viewport widths and text resizing. At the WCAG 2.2 AA reflow condition, ordinary content must work at 320 CSS pixels without two-dimensional scrolling, except for content that requires a two-dimensional layout.
- Check that user text-spacing overrides do not hide content or break functionality.
- Ensure sticky headers, banners, dialogs, and floating controls do not fully obscure keyboard focus or essential content.
- Provide a non-dragging alternative when dragging is needed to complete a task.
- Provide pause, stop, or hide controls for automatically moving, blinking, scrolling, or updating content when the applicable WCAG condition requires them.
- Check custom widgets against WAI-ARIA Authoring Practices for names, states, keyboard interaction, and focus handling.
- Test the completed flow with keyboard and relevant assistive technology. Automated checks alone are insufficient.

## 6. Target size and input methods

- Use the target size required or recommended by the target platform. For web content, WCAG 2.2 AA Target Size (Minimum) uses 24 by 24 CSS pixels with stated exceptions. Apple guidance commonly uses 44 by 44 points, or 60 by 60 points for visionOS buttons. Android guidance commonly uses 48 by 48 dp. These values are platform-specific and are not interchangeable.
- Give nearby actions enough spacing so users can select the intended control without accidental activation.
- Support the input methods people need for the product, such as keyboard, pointer, touch, switch, voice, controller, eye gaze, or stylus.
- Do not make a precise gesture, rapid tapping, long holds, simultaneous inputs, or analog-only movement the sole way to complete an important task. The main skill's smell tests already cover hover, focus, and touch feedback.
- Keep visual and spoken feedback available for actions, focus, state changes, and errors.

## 7. Adaptive layouts and localization

- Adapt content and component behavior to available space. Do not only scale a fixed phone screen for a tablet or desktop.
- When supported by the platform, review landscape, split-screen, resizable windows, foldables, tablets, external displays, and changes in posture or input.
- Account for safe areas, system bars, software keyboards, and persistent controls. Keep focused content visible when the keyboard opens.
- Check layout with translated text, text expansion, non-Latin scripts, and the fonts required for those scripts.
- For right-to-left locales, review reading order, alignment, bidirectional text, and directional icons. Mirror only elements whose meaning is directional.
- Use locale-aware date, time, number, currency, measurement, plural, and sorting formats.

## 8. Games, media, and spatial interfaces

- For games, offer suitable alternatives to fast repeated input, long holds, simultaneous buttons, or analog-only control. Consider remapping, adjustable timing, difficulty, and assistive input where they fit the game.
- For games and media, caption meaningful speech and sound cues, identify speakers when useful, and provide non-audio cues for important information. Consider audio description when visual information is required to understand prerecorded content.
- For spatial interfaces, keep important information within a comfortable field of view and reachable space.
- Support seated, standing, one-handed, or low-movement use where the experience allows it. Provide alternate locomotion when movement is needed.
- Avoid unexpected world or camera motion. Where motion is necessary, offer comfort settings and check frame stability on the target hardware.
- Do not make spatial audio the only way to locate or understand an important event.

## 9. Permissions, privacy, and human-AI interaction

- Ask for a device permission when the related feature needs it. Explain the purpose in context and design a usable denial path.
- Tell users what data a flow needs, how it affects the task, and what choices they have. Refer legal policy details to release-readiness.md.
- For AI interactions, set expectations about capabilities and limits. Make uncertainty, failures, and generated content understandable where they affect user decisions.
- Let users inspect and correct AI output. Preview consequential actions and provide cancel, undo, or human review where appropriate.
- Test first-use, repeated-use, incorrect-output, empty-result, delay, refusal, and recovery states for AI features.
- Avoid designing interface pressure that tricks users into sharing data, accepting a recommendation, or taking an irreversible action.

## 10. Design systems and shared components

- Document component purpose, when to use it, content rules, variants, interaction states, responsive behavior, and accessibility requirements.
- Use semantic design tokens for roles such as text, surface, focus, warning, and success. Check every supported theme.
- Test a shared component in its actual product context. A component library does not make every integration accessible or usable.
- Review long text, empty content, loading, errors, disabled states, high zoom, and translated content before standardizing a component.
- Give shared components an owner and a clear lifecycle. Research and test a proposed pattern before making it the default.

## 11. Web performance and resilience

- When web performance is in scope, measure field Core Web Vitals separately for mobile and desktop. web.dev currently uses the 75th percentile and targets LCP at or below 2.5 seconds, INP at or below 200 milliseconds, and CLS at or below 0.1. These are web performance indicators, not universal measures of usability.
- Reserve layout space for images, embeds, and other late-loading content. Check that fonts and media do not move or hide the task.
- Review critical flows on representative lower-powered devices and constrained networks when those conditions are part of the audience.
- For offline or unreliable network use, show which actions are pending, saved, failed, or require retry. Preserve work and prevent duplicate submissions where possible.

## 12. Evaluation and reporting

- Test whether users can complete important tasks, recover from errors, and understand consequences.
- Choose research methods that answer a specific question. Do not run research that the team cannot act on.
- Include disabled users and assistive technology in research when relevant. Do not infer accessibility from a single persona or scanner.
- Combine expert review, automated tools, and manual testing. Report which method ran and which did not.
- Use field data to find performance or task issues, segmented by device or context where it helps and privacy permits.
- Record evidence, uncertainty, and tradeoffs. Do not turn a heuristic, platform example, or checklist into a claim of user validation.

## Research sources

Check current versions and applicability before relying on these sources. Standards, platform guidance, and empirical findings have different scopes.

- Human-centred design and interaction principles: [ISO 9241-210](https://www.iso.org/cms/%20render/live/en/sites/isoorg/contents/data/standard/07/75/77520.html) and [ISO 9241-110](https://www.iso.org/cms/%20render/live/en/sites/isoorg/contents/data/standard/07/52/75258.html).
- User needs, moderated testing, and prototyping: [GOV.UK user needs](https://www.gov.uk/service-manual/user-research/start-by-learning-user-needs), [moderated usability testing](https://www.gov.uk/service-manual/user-research/using-moderated-usability-testing), and [prototyping](https://www.gov.uk/service-manual/design/making-prototypes).
- Web accessibility and widgets: [WCAG 2.2](https://www.w3.org/TR/WCAG22/), [WAI-ARIA Authoring Practices](https://www.w3.org/WAI/ARIA/apg/), and [WCAG 2.2 guidance](https://www.w3.org/WAI/standards-guidelines/wcag/new-in-22/).
- Platform target size, adaptive layout, and accessibility: [Apple UI design tips](https://developer.apple.com/design/tips/), [Apple buttons](https://developer.apple.com/design/human-interface-guidelines/buttons), [Android accessibility](https://developer.android.com/guide/topics/ui/accessibility/index.html), and [Android adaptive layouts](https://developer.android.com/design/ui/mobile/guides/layout-and-content/adapt-layout).
- Games and spatial experiences: [Xbox Accessibility Guidelines](https://learn.microsoft.com/gaming/accessibility/guidelines), [Android XR comfort](https://developer.android.com/design/ui/xr/guides/considerations), and [Apple spatial layout](https://developer.apple.com/design/human-interface-guidelines/spatial-layout/).
- AI product interaction: [Microsoft HAX guidelines](https://www.microsoft.com/en-us/haxtoolkit/ai-guidelines/), [the 2019 HAX study](https://doi.org/10.1145/3290605.3300233), and [Google People + AI Guidebook](https://pair.withgoogle.com/guidebook-v2/chapters).
- Shared systems, inclusive design, and web performance: [GOV.UK Design System](https://design-system.service.gov.uk/), [USWDS design principles](https://designsystem.digital.gov/design-principles/), and [Core Web Vitals](https://web.dev/articles/vitals).

Research source snapshot: 2026-10-09.
