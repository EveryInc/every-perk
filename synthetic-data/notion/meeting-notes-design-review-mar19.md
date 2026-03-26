# Design Review — Expense Categorization Confidence UI

**Date:** March 19, 2026
**Attendees:** Marina Rybalko, Nurdan Fatoglu, Pieter Odink, Alex Walker
**Location:** Figma / Zoom

---

## Context

Marina walked through the three confidence states for the Smart Expense Categorization UI. This is the design that pairs with SPEND-142 (ML model integration) and SPEND-143 (confidence thresholds).

## Auto-Applied State (Confidence > 85%)

Marina showed the pre-filled category with a subtle "AI" badge. Discussion:

- Pieter: "I like how understated the badge is. We don't want users thinking about AI — we want them thinking 'oh great, it's already done.'"
- Nurdan asked whether the badge should be removable/dismissible. Marina said no — it persists as an audit trail so finance teams know which categories were AI-assigned vs manual.
- Alex raised a good point: if a user overrides an auto-applied category, do we capture that as training data? Nurdan confirmed yes — every override goes back into the training pipeline.
- **Decision:** The AI badge stays visible but non-interactive. Tapping the category opens the override flow.

## Suggestion State (Confidence 60-85%)

Three category pills shown below the expense, user taps to confirm. "Other" expands the full picker.

- Marina tested this in internal dogfooding. 8/10 people said it felt "fast and natural."
- Pieter flagged: what happens if all 3 suggestions are wrong? User taps "Other," which feels like a failure moment. Marina suggested adding a micro-animation: the pills slide away and the full picker slides in. Makes it feel intentional, not like an error.
- Nurdan: "We should log when all three suggestions are rejected. That's our worst-case signal for model quality."
- **Decision:** Add the slide transition animation. Log "all suggestions rejected" as a distinct event.

## Manual Fallback State (Confidence < 60%)

Standard category picker, same as today. No AI suggestions shown.

- Pieter: "This is fine. Don't overcomplicate the fallback."
- Alex asked if we should show a message like "We couldn't auto-detect the category" — Marina strongly against. "That draws attention to a limitation. Just show the normal picker. Users won't even know AI was attempted."
- **Decision:** No messaging in the fallback state. Silent fallback.

## Override Flow Discussion

Pieter raised his key concern: when a user overrides an auto-applied category, it needs to be clear to the system that this is a **correction**, not just browsing. The training data needs clean signals.

Current flow: user taps category → full picker opens → user selects new category → done. Problem: we can't distinguish "I opened the picker to check, then closed it without changing" from "I opened the picker, browsed, and selected the same category."

Marina proposed a two-step override: (1) user taps the category, a small confirmation appears: "Change category?" with Yes/No. If Yes, the picker opens. This gives a clean signal.

- Nurdan loved this. Cleanly separates "I'm correcting this" from "I was just curious."
- Pieter: "Ship it."
- **Action:** Marina to add the two-step override confirmation to Figma mocks by March 21.

## Accessibility Review

- All states pass WCAG AA contrast ratios.
- Suggestion pills have visible focus states for keyboard navigation.
- Screen reader: each pill reads as "[Category name], suggestion [1/2/3], tap to select."
- **Action:** Marina to add screen reader labels to the Figma annotations.

## Open Questions

1. **Animation timing for suggestion confirmation** — Marina prototyped a gentle checkmark animation when a suggestion is selected. Concern: might be too playful for a finance tool. Nurdan thinks it's fine. Pieter says test it with 3 more people before deciding.
   - **Action:** Marina to run 3 more dogfood tests of the check animation and report back at the March 26 review.

2. **Dark mode** — Suggestion pills need different styling for dark mode. Not urgent but Marina wants to get it right before shipping.
   - **Action:** Marina to create dark mode variants by Sprint 25.

3. **Tablet layout** — The suggestion pills work well on phone and desktop but look awkward on tablet in portrait orientation. Too much horizontal space.
   - **Action:** Marina to adjust tablet layout. Low priority — only 4% of users are on tablet.

---

## Action Items Summary

| Action | Owner | Due |
|--------|-------|-----|
| Add two-step override confirmation to Figma | Marina | March 21 |
| Add screen reader labels to Figma annotations | Marina | March 21 |
| Run 3 more dogfood tests of check animation | Marina | March 26 |
| Create dark mode variants for suggestion pills | Marina | Sprint 25 |
| Adjust tablet layout for suggestion pills | Marina | Sprint 25 (low pri) |
| Log "all suggestions rejected" as distinct analytics event | Nurdan | Before launch |
| Verify override data feeds into training pipeline | Nurdan + Tomas | Before launch |
