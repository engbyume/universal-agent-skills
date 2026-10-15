# Website launch baseline and optional enhancements

## Public website launch baseline

Apply this baseline to every website intended for public release unless the user explicitly says it is desktop-only. Complete these checks before release.

- **Mobile optimization:** Build responsive layouts and tune navigation, typography, images, controls, and loading for narrow screens and touch. Check for clipped content, horizontal overflow, difficult controls, and oversized or slow assets at mobile widths. Verify the main flow at a phone-sized viewport. Use a real device when available.
- **Custom 404:** Provide a branded, helpful not-found page with a clear next step. Ensure unknown URLs return HTTP 404. Verify that the host does not return HTTP 200 for missing routes.
- **Page metadata:** Set a unique, accurate page title and meta description for every page and route, including the 404 page. Avoid placeholders and duplicates. For private or non-public pages, keep descriptive metadata and apply intentional noindex where appropriate. Search engines may use page text instead of the provided description.
- **Sitemap:** Generate and maintain a valid sitemap.xml with canonical, public, indexable URLs only. Update it when public routes or content change. Exclude private, preview, deleted, and noindex pages.
- **Search Console:** For each public, indexable site, create or use its Search Console property, verify ownership when authorized, submit the deployed sitemap, and review its processing status and indexing issues. Sitemap submission is a discovery hint and does not guarantee indexing. If sign-in or ownership verification needs user access, tell the user which step is needed and continue other safe work. Never request passwords or claim setup is complete without readback. Do not register private or intentionally non-indexable sites.
- **Structured data:** Add accurate site-level structured data for the real organization or website when those facts and a suitable type exist. Add page-specific structured data when a supported type fits. Keep markup consistent with visible content and validate it with the current official testing tools. Do not add irrelevant or invented business details, ratings, reviews, or claims. Valid markup does not guarantee a rich result.
- **Primary CTA:** Give each public marketing page one clearly dominant call to action that matches its goal. The same action may appear in more than one section. Keep navigation and necessary product actions visually secondary. Do not add competing primary actions or invent a conversion action for utility pages.

## Official search guidance

- [Mobile sites and mobile-first indexing](https://developers.google.com/search/docs/crawling-indexing/mobile/mobile-sites-mobile-first-indexing)
- [How to write meta descriptions](https://developers.google.com/search/docs/appearance/snippet)
- [Build and submit a sitemap](https://developers.google.com/search/docs/crawling-indexing/sitemaps/build-sitemap)
- [General structured data guidelines](https://developers.google.com/search/docs/appearance/structured-data/sd-policies)
- [Custom 404 pages and crawling errors](https://developers.google.com/search/docs/crawling-indexing/troubleshoot-crawling-errors)
- [Search Console setup and use](https://developers.google.com/search/docs/monitor-debug/search-console-start)
- [Verify site ownership in Search Console](https://support.google.com/webmasters/answer/9008080)

## Optional website enhancements

Use these ideas when they solve a real user need. Do not add them as a checklist. First check the site's purpose, content, audience, platform, accessibility, privacy, and implementation constraints. Prefer native platform behavior and the smallest interaction that works.

| Feature | Use when | Design safeguards |
|---|---|---|
| Dark mode toggle | The audience benefits from a choice of light and dark themes. | Respect the system preference, keep both themes readable, and remember the user's choice only when appropriate. |
| Cookie banner | The site uses cookies or similar storage that requires notice or consent. | Keep the notice concise, offer clear required choices, link to details, and avoid dark patterns. Do not show it as decoration. |
| Site search | Users need to find content across a collection or a large site. | Define what search covers and provide useful empty, loading, error, and no-results states. |
| Back-to-top button | A long page makes returning to the top slow. | Keep it out of the way, label it for assistive technology, and make it keyboard accessible. |
| Mobile menu | The full navigation does not fit the small-screen layout. | Provide a clear open and close action, manage focus, support Escape, and keep touch targets usable. |
| Loading animation | An action takes long enough that users need feedback. | Show a truthful status or progress value. Keep motion brief and respect reduced-motion settings. |
| Hover states | Pointer users need feedback on interactive elements. | Keep feedback subtle. Provide equivalent focus and touch feedback; do not hide information behind hover. |
| Scroll progress bar | A long article or guided flow benefits from position feedback. | Make progress accurate, unobtrusive, and available without relying on color or motion alone. |
| Copy-to-clipboard button | Users often reuse a visible value, such as a code sample or link. | Copy only the displayed value after an explicit action, then announce success or failure accessibly. |
| Print stylesheet | Users may print or save a content-focused page. | Preserve meaningful content and links; remove controls and navigation that do not help on paper. |
| Sticky header | Persistent navigation helps users on long pages. | Prevent it from covering content or anchor targets. Check small screens, zoom, and keyboard focus. |
| Skip-to-content link | A page repeats navigation before its main content. | Make it the first keyboard stop and reveal it clearly on focus. |
| Password visibility toggle | A form contains a password field and users may need to check their entry. | Use a labeled button, expose its state, and keep the input's password semantics intact. |
| UTM tracking | Campaign attribution is an approved product requirement. | Do not add tracking by default. Avoid sensitive values, respect consent and privacy controls, and prevent parameters from breaking navigation. |
| Form success state | The server confirms that a form submission succeeded. | State what happened and the next step. Do not report success before confirmation. |
| Form error state | Validation or submission fails. | Explain the problem in plain language, preserve entered values where safe, and offer a useful correction. Do not use color alone. |
| Confirmation dialog or modal | An action is destructive, costly, or hard to undo. | Do not interrupt routine actions. Explain the consequence, provide a clear cancel path, and manage focus accessibly. |
| Last-updated date | Content changes over time and freshness affects trust or decisions. | Use the actual content date and a clear locale or timezone where timing matters. Omit it on stable pages. |
| Expandable FAQ | A set of secondary answers can stay out of the way until requested. | Use accessible disclosure controls, descriptive labels, and a clear expanded state. Keep essential information visible. |
| Floating contact button | Contact is a primary action for this page or service. | Keep it from covering content or controls, especially on mobile, and provide a descriptive accessible name. |

Some features become baseline when their matching interface exists. Forms need clear success and error feedback. Pages with repeated navigation need a skip link. Cookie notices and tracking depend on the actual storage and privacy requirements. Add only the relevant behavior.
