# Figma Design Status — Spend & Control Squad

**Last updated:** March 24, 2026
**Designer:** Marina Rybalko

---

## Smart Expense Categorization — Confidence UI

**File:** Expense Categorization — Confidence Patterns
**Status:** In Review — awaiting PM sign-off (March 26 review scheduled)

### Screens designed:
1. **Auto-applied state** — Category pre-filled with subtle "AI" badge, one-tap to override. Minimal friction.
2. **Suggestion state** — Top 3 category suggestions shown as pills, user taps to confirm. "Other" option expands full picker.
3. **Manual fallback** — Standard category picker, no AI suggestions shown. Same as current experience.

### Design review notes (from Marina, March 20):
- Kept the AI badge intentionally subtle. Users shouldn't feel like the system is making decisions for them — it should feel like a helpful pre-fill.
- Suggestion pills tested well in internal dogfooding. 8/10 testers said it felt "fast and natural."
- Open question: should we animate the transition from suggestion to confirmed? I prototyped a gentle check animation but it might be too much. Will discuss with Nurdan.
- Accessibility: all states pass WCAG AA contrast. Suggestion pills have focus states for keyboard nav.

### Feedback from Pieter (async, March 22):
"Looks great. My only concern is the override flow — if a user overrides the auto-applied category, is it obvious that they're correcting the AI? We want to capture clean training data from overrides."

**Action:** Marina to add a micro-interaction that distinguishes "I'm browsing categories" from "I'm correcting a wrong suggestion."

---

## Policy Engine v2 — Rule Builder UI

**File:** Policy Engine — Rule Builder
**Status:** In Progress — eng build started, Figma is source of truth

### Screens designed:
1. **Rule list view** — All active rules in a table with status, conditions summary, and toggle to enable/disable.
2. **Rule editor** — Step-by-step builder: select condition type → define threshold → choose action (auto-approve / require approval / block) → assign approver.
3. **Approval chain config** — Drag-and-drop approver sequence. Shows estimated approval time based on historical data.
4. **Rule conflict warning** — If a new rule contradicts an existing one, surface a clear warning with "which rule wins" resolution.

### Design review notes (from Marina, March 19):
- The step-by-step builder tested much better than the original "form with all fields visible" approach. Less overwhelming for admins.
- Rule conflict detection is the trickiest UX challenge. Current approach: inline warning banner with a "Compare rules" expandable section.
- Pieter wants us to consider a "preview mode" where admins can see which past expenses would have been affected by a new rule. Great idea, but adds scope — flagged as a fast-follow.

---

## Group Booking Flow v2 — Shipped

**File:** Group Booking — v2 Final
**Status:** Shipped (March 18). File archived to "Shipped" section.

### Post-launch design notes:
- The traveler preference selection step has the highest drop-off (32%). Reviewing whether the layout is too information-dense. Possible simplification: collapse advanced preferences (seat, meal, loyalty number) behind an "Add preferences" expandable, so the default is just "Confirm your trip."
- Mixed cabin class edge case (SPEND-120): current UI doesn't clearly communicate when group members have selected different classes. Need a visual indicator — maybe a split badge on the group summary card.
