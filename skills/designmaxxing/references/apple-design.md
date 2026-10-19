# Apple design review

This is a mandatory interaction and craft review for every task using `designmaxxing`. Apply Apple-specific conventions only when they fit the product, platform, user direction, and accessibility needs. It is a design lens, not a default Apple visual theme.

## Source and scope

This reference distills the external [`apple-design` skill](https://github.com/emilkowalski/skills/blob/e8a175de22ae1e49370fc144c1f3bb9aeedf988d/skills/apple-design/SKILL.md) from the [emilkowalski/skills repository](https://github.com/emilkowalski/skills). That audited source translates Apple's fluid-interface ideas for the web. For native Apple software, also follow current Apple Human Interface Guidelines and platform APIs. The external source was statically audited and not installed or executed.

## Required review

- **Feedback and direct manipulation:** Show meaningful input feedback at pointer or touch down. For drags, use Pointer Events and capture when supported, preserve the grab offset, and keep content aligned with the input throughout movement. Use a small movement threshold and let users cancel a gesture where appropriate.
- **Interruptible motion:** Let users reverse or redirect an interaction in progress. Start retargeted motion from the current rendered position, preserve release velocity where the animation system supports it, and avoid locking input while an element moves. Prefer an animation model that can retarget smoothly for gesture-driven motion; simple state transitions do not need a spring.
- **Use motion to explain behavior:** Use springs for interactions that need continuous retargeting. Keep axes independent when their motion and velocity differ. Preserve spatial consistency between entry and exit. Project momentum and use soft edge resistance only when the user gesture and product behavior call for them.
- **Keep motion responsive:** Avoid blocking work on the input path. Use display-synchronized updates for frame-driven interaction and favor compositor-friendly properties such as transforms and opacity when they fit the implementation.
- **Coordinate feedback:** When the platform supports sound or haptics, align them with the action that caused them and reserve them for meaningful events.
- **Respect accessibility preferences:** Provide a reduced-motion equivalent. Respect reduced-transparency and increased-contrast preferences where supported. Keep keyboard access, focus, hit areas, and scalable text usable.
- **Use materials with purpose:** Blur and translucency may show functional hierarchy when they fit the product. Preserve contrast and avoid stacking translucent surfaces. The existing rule against liquid glass as a default remains in force.
- **Adapt typography to context:** System fonts may be a good platform fit. Adjust optical sizing, tracking, line height, and layout to the text size, script, brand, and platform. Respect user text scaling.
- **Preserve user agency and orientation:** Make state changes clear, support undo for recoverable mistakes, keep navigation predictable, protect privacy, and place controls near the content they affect.
- **Prototype and inspect:** Build interaction and visual treatment together. Review motion at normal and slowed playback. Do not claim user testing unless it occurred.

Treat numeric motion settings in the source as starting examples. Tune against the product's input methods, platform behavior, performance, and reduced-motion needs. Do not apply motion or translucent materials solely because this reference exists.
