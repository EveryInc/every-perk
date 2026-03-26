# Product Strategy: Spend & Control — H2 2026

**Author:** Pieter Odink
**Status:** DRAFT v2 — For leadership review
**Created:** March 10, 2026
**Last updated:** March 22, 2026

---

## Executive Summary

Spend & Control is at an inflection point. We've built a solid foundation in expense management and travel booking, but **AI is reshaping competitive dynamics** and we risk losing our position if we don't move faster.

This strategy proposes three strategic bets for H2 2026:
1. **AI-First Expense Experience** — Make manual expense work disappear
2. **Platform Play** — Open Perk's policy and data infrastructure to third-party tools
3. **Enterprise Moat** — Deepen compliance and governance features that competitors can't easily replicate

Combined, these bets position Perk as the **modern-enterprise standard** — the AI sophistication of Brex/Ramp with the compliance depth of Concur.

---

## Strategic Context

### Market Position (H1 2026)

- ARR: €42M (Spend & Control features account for ~60%)
- Active customers: 2,800+
- Active travelers: 20,200
- NPS: 34 (up from 28 in Q4 2025)
- Gartner MQ position: "Niche Player" (targeting "Visionary" by year-end)

### Competitive Pressure

Navan launched AI features in January. Brex raised $300M on an "AI-native" narrative. SAP Concur is shipping AI in June. **The window for differentiation is closing.**

Our advantage: we're the only platform that combines modern UX + enterprise compliance. But that advantage erodes if our UX isn't AI-powered.

### Customer Signal

Top 3 customer requests (Q1 2026 feedback synthesis):
1. Auto-categorization (89 mentions)
2. Better policy explanations (54 mentions)
3. Faster mobile experience (47 mentions)

Three of our top 20 accounts mentioned evaluating Navan. One account (Meridian, $180K ARR) has renewal conditional on AI categorization shipping.

---

## Strategic Bet 1: AI-First Expense Experience

**Goal:** Eliminate manual work from expense submission. Target: 80%+ of expense line items require zero manual categorization by end of 2026.

### H2 Initiatives

| Initiative | Description | Target | Owner |
|-----------|-------------|--------|-------|
| AI Categorization v2 | Expand from single-category to multi-category (GL + client billing) | End Q3 | Nurdan |
| Smart Receipt Processing | On-device OCR + preprocessing (close Navan mobile gap) | End Q3 | Tomas |
| AI Travel Assistant | Conversational expense + policy queries in app + Slack | End Q4 | Tudor |
| Predictive Expense Flagging | Proactively flag unusual expenses before submission | End Q4 | Nurdan |

### Dependencies
- AI Categorization v1 (SPEND-142) must ship in Q2 as planned
- Mobile SDK upgrade for on-device ML (requires iOS 18+ / Android 15+)
- AI Gateway infrastructure (see Platform Play below)

### Success Metrics
- Miscategorization rate: 23% → under 5%
- Avg submission time: 252s → under 90s
- Mobile OCR accuracy: 81% → 95%+

---

## Strategic Bet 2: Platform Play

**Goal:** Transform Perk from a product into a platform. Open our policy engine, expense data, and booking infrastructure to third-party tools via APIs.

### H2 Initiatives

| Initiative | Description | Target | Owner |
|-----------|-------------|--------|-------|
| Policy Engine API | Public API for querying and enforcing spend policies | End Q3 | Neil |
| Expense Data API | Structured access to expense data for ERP integrations | End Q3 | Lydia |
| SAP Integration | Bidirectional sync with SAP S/4HANA | End Q4 | New PM (hire) |
| NetSuite Integration | Bidirectional sync with NetSuite | End Q4 | New PM (hire) |
| Webhook Events | Real-time events for expense submission, approval, policy violations | End Q3 | Tudor |

### Dependencies
- Requires 1 new PM hire (approved in headcount plan — see Leadership Sync notes)
- API gateway infrastructure (shared with Platform team)
- Partner agreements with SAP and NetSuite

### Success Metrics
- 3+ third-party integrations live by end of 2026
- 20% of customers using at least one integration
- API adoption: 500+ API calls/day within 3 months of launch

### Risks
- **Scope creep.** ERP integrations are notoriously complex. Each integration could take 3-4 months instead of the planned 2.
- **Cannibalization.** If SAP integration is too good, enterprise customers might use Perk for booking only and SAP for expenses. Need to ensure the integrated experience is better than standalone.

---

## Strategic Bet 3: Enterprise Moat

**Goal:** Build compliance and governance features that make it prohibitively expensive for enterprise customers to switch away from Perk.

### H2 Initiatives

| Initiative | Description | Target | Owner |
|-----------|-------------|--------|-------|
| Policy Engine v3 | Client-context rules, multi-entity support, delegation | End Q4 | Neil |
| Compliance Dashboard | Real-time compliance posture + audit trail | End Q3 | Agustina |
| SOC 2 Type II Certification | Formal compliance certification | End Q4 | Security team |
| Multi-Entity Reporting | Consolidated reporting across legal entities | End Q4 | Lydia |
| Advanced Approval Workflows | Conditional routing, delegation, escalation | End Q3 | Mauro |

### Dependencies
- Policy Engine v2 (SPEND-155) must ship in Q2
- SOC 2 requires security team bandwidth (shared resource)

### Success Metrics
- Enterprise customer retention: 95%+
- Reduce enterprise onboarding time by 40%
- Pass 3+ enterprise compliance audits using Perk's native features

---

## Resource Plan

### Current Team (10 people)
- 5 PMs (Pieter, Neil, Nurdan, Alex, Tudor, Mauro, Lydia — wait, that's 7)
- 1 Designer (Marina)
- 1 Product Ops (Agustina)
- 1 Eng Lead (Tomas)

### Requested Additions
- 1 Senior PM for ERP integrations (approved, recruiting)
- 1 Senior Product Designer (approved, recruiting)
- 1 Data Analyst to support Agustina (NOT yet approved — will request in Q3 planning)

### Allocation
| Person | H2 Focus | % Time |
|--------|----------|--------|
| Nurdan | AI-First Expense (Bet 1) | 100% |
| Tudor | AI Travel Assistant + Webhooks (Bet 1 + 2) | 100% |
| Neil | Policy Engine v3 + Policy API (Bet 2 + 3) | 100% |
| Alex | Group Booking optimization (maintenance) | 50% |
| New PM | SAP + NetSuite integrations (Bet 2) | 100% |
| Mauro | Approval Workflows (Bet 3) | 80% |
| Lydia | Expense Data API + Multi-Entity Reporting (Bet 2 + 3) | 100% |
| Marina | AI UX + Enterprise UX | 100% |
| Agustina | Dashboard + Metrics | 100% |
| Tomas | Smart Receipt Processing + Platform APIs | 100% |

**Gap:** Alex is only 50% allocated. The remaining 50% is unplanned — could absorb overflow or start on a new initiative. This should be decided at Q3 planning.

---

## Timeline

```
        Q2 2026                    Q3 2026                    Q4 2026
Apr     May     Jun     Jul     Aug     Sep     Oct     Nov     Dec
|-------|-------|-------|-------|-------|-------|-------|-------|-------|
|< AI Cat v1 >|                                                       |
|       |< Policy Engine v2 >|                                        |
|       |       |< AI Cat v2 (multi-cat) ----->|                      |
|       |       |< Smart Receipt Processing -->|                      |
|       |       |       |< Policy Engine API ->|                      |
|       |       |       |< Expense Data API -->|                      |
|       |       |       |       |< SAP Integration ------->|          |
|       |       |       |       |< NetSuite Integration -->|          |
|       |       |       |< Compliance Dashboard >|                    |
|       |       |       |       |< AI Travel Assistant ------------>| |
|       |       |       |       |       |< Policy Engine v3 ------->| |
|       |       |       |       |       |< SOC 2 Type II ---------->| |
```

---

## Open Questions

1. **Should we build or buy the on-device OCR?** Building gives us control but takes 3+ months. Acquiring (like Navan did) is faster but expensive. Tomas is evaluating open-source alternatives.

2. **How do we price the platform APIs?** Free for all customers? Premium tier? Per-call? Need to align with commercial team.

3. **Is the AI Travel Assistant a Q4 or 2027 initiative?** Tudor's brief is compelling but we're already stretching. Pieter suggests conditional: if Bet 1 and Bet 2 are on track by August, green-light the assistant. Otherwise, defer to Q1 2027.

4. **Multi-entity reporting: build on Looker or build native?** Lydia argues for native (better UX, data stays in platform). Agustina argues for Looker (faster, more flexible). Need to decide by July.

5. **The team count doesn't add up.** The "Current Team" section says 10 people but lists more names than that. Also, Alex is listed as PM but the squad wiki shows him as "PM — Bookings" with a full-time role. Need to reconcile the team structure.

---

## Appendix: What We're NOT Doing in H2

- Corporate cards (strategic but too big for this cycle)
- International expansion (maintaining current 80+ countries, not adding new ones)
- Consumer/personal expense features (staying B2B)
- Custom reporting builder (Looker/Amplitude serve this adequately for now)
