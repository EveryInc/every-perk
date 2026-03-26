# Roadmap: Spend & Control — Q2–Q3 2026

**Owner:** Pieter Odink
**Last updated:** March 8, 2026
**Status:** APPROVED (LT sign-off March 6)

---

## ⚠️ NOTE: This roadmap was approved on March 6 and reflects the plan as of that date. Some dates may have shifted since approval — check Jira for current status.

---

## Q2 2026 (April – June)

### Must-Ship (P0)

| Initiative | Target Date | Owner | Status |
|-----------|-------------|-------|--------|
| Smart Expense Categorization v1 (SPEND-142) | **April 8** | Nurdan | On track |
| Policy Engine v2 (SPEND-155) | **May 15** | Neil | Blocked (Payments API) |
| Mobile receipt camera improvements (SPEND-162) | **April 20** | Tomas | On track |
| Slack bot — weekly summary (SPEND-161) | **April 1** | Tudor | On track |

### Should-Ship (P1)

| Initiative | Target Date | Owner | Status |
|-----------|-------------|-------|--------|
| Group Booking — mixed cabin class (SPEND-120) | May 30 | Alex | Not started |
| Expense report pagination (enterprise timeout fix) | April 15 | Tomas | Not started |
| Approval chain notifications (SPEND-157) | June 1 | Mauro | Spec in progress |
| OCR multi-currency improvements (SPEND-148) | April 1 | Tomas | In review |

### Nice-to-Have (P2)

| Initiative | Target Date | Owner | Status |
|-----------|-------------|-------|--------|
| Dark mode for expense screens | June 30 | Marina | Not started |
| Expense export API improvements | June 30 | Lydia | Not started |

---

## Q3 2026 (July – September)

### Must-Ship (P0)

| Initiative | Target Date | Owner | Status |
|-----------|-------------|-------|--------|
| AI Categorization v2 (multi-category) | August 30 | Nurdan | Planning |
| Smart Receipt Processing (on-device OCR) | September 15 | Tomas | Exploration |
| Policy Engine API (public) | August 15 | Neil | Planning |
| Expense Data API | September 1 | Lydia | Planning |
| Compliance Dashboard | August 30 | Agustina | Not started |

### Should-Ship (P1)

| Initiative | Target Date | Owner | Status |
|-----------|-------------|-------|--------|
| Webhook events for expense lifecycle | July 30 | Tudor | Planning |
| Advanced approval workflows | September 15 | Mauro | Not started |
| SAP integration (Phase 1: export) | September 30 | New PM | Awaiting hire |

---

## Key Dependencies

1. **Payments API v3** → Policy Engine v2 (SPEND-155). ETA: April 4. Has slipped twice.
2. **PM hire** → SAP integration. Recruiting starts March.
3. **iOS 18 SDK** → On-device OCR. Apple releases final SDK in June.
4. **API gateway** → Platform APIs. Shared with Platform team, timeline TBD.

---

## Milestones

- **April 8:** AI Categorization v1 shipped → press release + customer comms
- **May 15:** Policy Engine v2 shipped → enterprise customer enablement
- **June 30:** Q2 complete → QBR readout
- **August 30:** AI Categorization v2 + Compliance Dashboard → Gartner MQ submission window
- **September 30:** Platform APIs live → partner onboarding begins

---

## Changes Since Last Version

| Date | Change | Reason |
|------|--------|--------|
| March 6 | Initial version approved | LT sign-off |
| March 8 | Updated Policy Engine v2 status to "Blocked" | Payments API v3 delay |
