# Sprint 23 Retrospective — Spend & Control

**Date:** March 18, 2026
**Facilitator:** Agustina Di Clemente
**Attendees:** Neil Rogers, Nurdan Fatoglu, Alex Walker, Marina Rybalko, Tudor Tise, Mauro Spadaro, Lydia Foster, Tomas Berger

---

## What went well 🟢

- **Group Booking v2 shipped on time.** The team hit the March 18 target that was set 6 weeks ago. Clean rollout, no rollbacks. Alex credits the phased feature flag approach — rolling from 10% → 50% → 100% over 3 days gave us confidence.
- **Cross-functional collaboration was strong.** Marina's design ↔ Tomas's eng handoff was smooth. Weekly design-eng syncs helped catch issues early.
- **Lydia's PDF fix was a quick win.** Small change, big customer impact. Took 2 days from ticket to deploy. Good example of prioritizing high-signal customer pain.
- **Sprint planning accuracy improved.** We committed to 34 story points and delivered 31. Best accuracy in 4 sprints.

## What didn't go well 🔴

- **OCR accuracy is still below target.** We planned to hit 90% by Sprint 23 end. We're at 81%. Multi-currency and handwritten receipts are harder than expected. Tomas flagged this early but we didn't adjust the timeline.
- **Policy Engine v2 blocked for 3 weeks.** The Payments API v3 dependency has slipped twice. The team has been building UI and rule logic but can't wire up the key feature (real-time checks). Feels like we're building a car without an engine.
- **The enterprise timeout issue should have been caught in QA.** GlobalTech's PDF generation timeouts have been reported since February. We underestimated the severity because our test data only had reports with 10-15 line items. Our test suite doesn't cover enterprise-scale data.
  - **Action:** Tomas to add enterprise-scale test fixtures (50, 100, 200 line items) to the test suite by Sprint 24 end.
- **Mauro's notification spec is 2 weeks overdue.** SPEND-157 was supposed to be specced by March 7. Still not started. Mauro acknowledged — he got pulled into platform migration work that wasn't planned.
  - **Action:** Mauro to complete SPEND-157 spec by March 25. Neil to protect Mauro's time from cross-squad requests.
- **Amplitude vs. backend discrepancy.** Agustina found that Amplitude shows a 64% group booking conversion rate while the backend calculates 68%. 4 percentage point difference. Likely caused by Amplitude excluding users who hit the flow from deep links (no page_view event fires). Need to reconcile.
  - **Action:** Agustina to investigate the Amplitude/backend conversion rate discrepancy and document the root cause by March 24.

## Action items from previous retro (Sprint 22) — Status check

| Action | Owner | Status |
|--------|-------|--------|
| Add monitoring alerts for PDF generation time | Tomas | ❌ NOT DONE — deprioritized for Group Booking push |
| Create runbook for enterprise account hotfixes | Lydia | ✅ Done |
| Sync with Payments team on API v3 timeline | Neil | ✅ Done (but timeline slipped again) |
| Document design handoff process in wiki | Marina | ❌ NOT DONE — will carry to Sprint 24 |
| Set up automated Slack alerts for support ticket spikes | Tudor | ✅ Done |

**Pieter's note (added async):** Two actions from Sprint 22 still not done. Let's not carry items more than one sprint. If it's not important enough to do this sprint, remove it from the list. If it IS important, make time for it.

---

## Decisions

1. **Enterprise test fixtures** are now a requirement for all new features. No feature ships without test data at 10x normal scale.
2. **Dependency blockers will be escalated after 1 week**, not 3. Neil's Payments API experience taught us we wait too long to escalate.
3. **Sprint retro actions get a specific due date**, not just "next sprint." Accountability is clearer with dates.

---

## Team Mood Check (1-5)

| Name | Score | Comment |
|------|-------|---------|
| Alex | 5 | "Great sprint. Shipping feels good." |
| Nurdan | 3 | "Frustrated about OCR. We're so close but not there." |
| Neil | 2 | "Blocked for 3 weeks is demoralizing. Need that API." |
| Marina | 4 | "Design work is going well. Proud of the Group Booking UI." |
| Tudor | 4 | "Slack bot is fun to build. Good feedback from the team." |
| Mauro | 3 | "Overcommitted. Need to learn to say no to platform requests." |
| Lydia | 4 | "Quick wins feel good. Want to tackle the timeout properly next." |
| Tomas | 3 | "OCR is a grind. Handwritten receipts are the final boss." |
| **Average** | **3.5** | |
