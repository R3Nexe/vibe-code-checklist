# Accessibility

ADA Title III lawsuits hit 4,600+ in 2025. The European Accessibility Act became enforceable across EU markets in June 2025. Treat WCAG 2.1 Level AA as the baseline standard ([source](https://blog.usablenet.com/2025-midyear-accessibility-lawsuit-report-key-legal-trends)).

## Core requirements

- Alt text on all meaningful images, empty `alt=""` for decorative images.
- Color contrast ratio of 4.5:1 minimum for regular text (WCAG AA).
- Full keyboard navigation for every interactive element.
- Semantic HTML using proper headings, landmarks, lists, and ARIA labels.
- Screen reader testing on common flows.

## Common gaps in generated code

- Missing focus indicators on interactive elements.
- Form inputs without associated `<label>` elements.
- Error messages not announced to screen readers (requires aria-live regions).
- Missing skip-to-content link for keyboard users.
- UI components built from unstyled divs instead of semantic buttons, headings, and lists.

## Practices to reject

- Never rely on accessibility overlay widgets (such as accessiBe or UserWay) for compliance. Regulators have issued enforcement penalties and courts repeatedly reject them as sufficient remediation ([source](https://blaksheepcreative.com/web-design/accessibility/ai-generated-website-ada-lawsuit/)).
