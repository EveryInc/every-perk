# PRD: Smart Expense AI v2 — Multi-Category & Predictive

**⚠️ DRAFT — DO NOT SHARE OUTSIDE THE SQUAD ⚠️**
**This is an early draft. Numbers are placeholder. Not reviewed by eng or design.**

**Author:** Nurdan Fatoglu
**Status:** DRAFT v0.3 — Incomplete
**Created:** March 20, 2026
**Last updated:** March 22, 2026

---

## Context

This PRD covers the v2 of our AI expense features, planned for Q3 2026. It builds on Smart Expense Categorization v1 (SPEND-142, shipping April).

**DO NOT SHARE THIS WITH CUSTOMERS.** Some of the ideas here might not ship. I'm still exploring what's feasible with Tomas.

---

## Problem

v1 solves single-category auto-categorization. But many of our enterprise customers need:
1. **Multi-category assignment** — Internal GL code + client billing code on the same expense
2. **Predictive flagging** — Catch unusual expenses before they're submitted, not after
3. **Smart suggestions** — Pre-fill common expense fields based on patterns

BrightPath told us they spend 15 hours/week adding client billing codes after the fact. GlobalTech wants anomaly detection on large expenses. Meridian wants the whole submission flow to be "basically zero touch."

---

## Proposed Solution

### Feature 1: Multi-Category AI

When submitting an expense, the AI assigns TWO categories:
- **Internal category** (existing — GL code, cost center)
- **Client/project category** (NEW — which client/project is this billable to?)

The AI determines the client/project from:
- The traveler's current trip (if expense is during an active trip, infer the client)
- The merchant (if the merchant is near a client's office, likely a client expense)
- Historical patterns (if this traveler always expenses restaurants near Client X as billable)

**Confidence tiers:** Same as v1 — auto-apply above 85%, suggest 60-85%, manual below 60%.

**Open question:** What if the expense is NOT billable to any client? Do we show a "Not billable" option or just skip the client category? Leaning toward auto-detecting non-billable expenses and hiding the field entirely.

### Feature 2: Predictive Expense Flagging

Before the user hits "Submit," the AI reviews the expense report and flags:
- **Anomalies:** Expenses that are unusually large for this category/merchant/traveler
- **Policy risks:** Expenses that are likely to violate a policy (based on historical approval patterns)
- **Duplicates:** Expenses that look like duplicates of previously submitted items
- **Missing receipts:** High-value expenses without attached receipts

This runs client-side (fast) with a server-side verification (thorough).

**Example:**
> "This dinner expense ($340 for 2 people) is higher than your typical client dinner ($80-120). You may want to add a justification note before submitting, as expenses over $200 require manager approval."

### Feature 3: Smart Field Pre-fill

Based on the receipt and context, pre-fill:
- **Date** (from receipt OCR — already doing this)
- **Merchant** (from receipt OCR — already doing this)
- **Amount + currency** (from receipt OCR — already doing this)
- **Category** (from AI — v1 is doing this)
- **Client/project** (from AI — NEW in v2)
- **Attendees** (from calendar data — if the expense date matches a meeting with a client, suggest attendees)
- **Justification** (auto-generate based on category + amount + context: "Client dinner with Acme Corp team, 4 attendees")

---

## Technical Approach (VERY ROUGH)

### Multi-Category
- Extend the existing ML model to output two category predictions
- Training data: need to build a mapping of expenses → client/project from customers who manually tag today
- **PROBLEM:** We don't have client/project tagging in our data model today. Need a schema change. This is probably a 3-sprint effort just for the data model.

### Predictive Flagging
- Anomaly detection model trained on per-user expense history
- Policy risk scoring: query the Policy Engine v2 API (dependency: SPEND-155 must be done first)
- Duplicate detection: fuzzy matching on date + amount + merchant
- **PROBLEM:** Running these checks client-side requires a lightweight model. On-device ML? WebAssembly? Need to talk to Tomas.

### Smart Pre-fill
- Calendar integration: need Google Calendar / Outlook API access
- Attendee suggestion: match expense date/time to calendar events with external attendees
- Justification generation: LLM-based, needs to be fast (<500ms)
- **PROBLEM:** Calendar data is PII. Privacy review needed. GDPR implications for EU travelers.

---

## Rough Effort Estimates

| Feature | Eng Effort | Design Effort | Data/ML Effort |
|---------|-----------|---------------|----------------|
| Multi-Category AI | 5-8 sprints (includes schema change) | 2 sprints | 3 sprints |
| Predictive Flagging | 3-5 sprints | 2 sprints | 2 sprints |
| Smart Pre-fill | 4-6 sprints | 1 sprint | 1 sprint |
| **Total** | **12-19 sprints** | **5 sprints** | **6 sprints** |

That's 12-19 eng sprints. At 2-week sprints, that's 6-10 months. **Way too much for Q3 alone.** Need to scope down.

**Scoping options:**
- A) Ship Multi-Category only in Q3, push Predictive and Pre-fill to Q4 → **my recommendation**
- B) Ship MVP of all three in Q3, iterate in Q4 → risky, might ship half-baked features
- C) Combine with AI Travel Assistant (Tudor's initiative) → bigger vision but bigger effort

---

## Success Metrics (Placeholder — Need to Validate)

- Multi-category accuracy: >80% for client/project assignment
- Predictive flagging: catch 60%+ of policy violations before submission
- Smart pre-fill: reduce manual field entry by 70%
- Overall submission time: under 60 seconds (from current 252s)

---

## Risks

1. **Data model schema change** for multi-category is a breaking change. Needs migration plan.
2. **Calendar integration** requires privacy review and customer consent. Could add 2-3 months.
3. **Model training data** for client/project assignment is sparse. Only ~30% of customers use client tagging today.
4. **Scope.** This PRD describes 12-19 sprints of work. That's more than one squad can handle in one quarter. Need to be ruthless about priorities.
5. **Dependency on v1.** If SPEND-142 is delayed or the model accuracy disappoints, v2 plans need to adjust.

---

## TODO (Nurdan's Notes to Self)

- [ ] Talk to Tomas about on-device ML feasibility
- [ ] Get privacy review started for calendar integration (this will take forever, start NOW)
- [ ] Pull client/project tagging data from top 10 customers to assess model training feasibility
- [ ] Schedule whiteboard session with Marina on the predictive flagging UX
- [ ] Talk to BrightPath (Robert) about their multi-category workflow to validate the approach
- [ ] UPDATE THE TEAM HEADCOUNT NUMBERS — this doc references the wrong team size from the strategy draft (it says 10 people but we actually have 10 IC roles + Pieter as lead = 11)
