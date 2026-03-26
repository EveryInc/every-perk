# Spend & Control — Weekly Sync

**Date:** March 21, 2026
**Attendees:** Neil Rogers, Nurdan Fatoglu, Alex Walker, Marina Rybalko, Tudor Tise, Agustina Di Clemente, Mauro Spadaro, Pieter Odink

---

## Group Booking v2 — Post-Launch Check-in

Alex shared early numbers. Since shipping on March 18:
- 847 group bookings created (vs ~200/week on the old flow)
- Conversion rate: 68% (up from 41%)
- Avg group size: 6.2 travelers
- Main drop-off point: traveler preference selection step (32% abandon there)
- 14 support tickets related to mixed cabin class edge case (SPEND-120)

Agustina is building the metrics dashboard (SPEND-119) to track this ongoing. Should be live by end of Sprint 24.

**Action:** Alex to write a brief for the drop-off analysis — is it UX friction or just travelers who were invited but not interested?

## Smart Expense Categorization Update

Nurdan walked through current state. Model accuracy is promising but blocked on OCR (SPEND-148):
- Tomas says OCR accuracy is at 81% now, up from 74%. Multi-currency is the remaining gap.
- Design review with Marina scheduled for March 26 — confidence UI patterns.
- Nurdan flagged risk: if OCR doesn't hit 90% by April 1, we should discuss whether to ship with wider manual fallback ranges.

**Action:** Nurdan + Tomas to do a focused OCR accuracy sprint this week targeting multi-currency receipts.

## Policy Engine v2

Neil gave the update. Rule builder UI is in good shape (Marina's Figma is nearly final), but the whole feature is blocked:
- Payments API v3 real-time balance check endpoint not ready. Payments team gave April 4 as ETA.
- Neil has escalated to Pieter. Pieter confirmed he'll follow up with Payments lead this week.
- In the meantime, eng can continue building the UI and rule logic — just can't wire up the real-time checks.

**Action:** Pieter to sync with Payments team lead by March 24.
**Action:** Mauro to spec the notification flow (SPEND-157) so it's ready when the block clears.

## Slack Bot Weekly Summary (Tudor)

Tudor demoed the current version. Posts to #finance-leads every Monday with:
- Total spend by category (top 5)
- Largest individual expenses
- Policy violations flagged that week

Feedback: Pieter wants it to also include a week-over-week comparison. Tudor will add that in Sprint 25.

## Misc

- Lydia shipped the PDF export fix (SPEND-160). No more broken currency symbols.
- Tomas is also improving the mobile receipt camera (SPEND-162) — auto-crop is working, perspective correction next.
- Next sync: March 28.
