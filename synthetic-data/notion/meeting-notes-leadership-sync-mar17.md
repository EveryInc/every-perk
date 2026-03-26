# Leadership Sync — Product & Design Org

**Date:** March 17, 2026
**Attendees:** Sarah Chen (VP Product), Pieter Odink, Rosa Jimenez (Director of Design), Erik Lindqvist (Director of PM — Growth), Carmen Vega (Director of PM — Platform), Lena Schulz (Head of Product Ops)
**Note-taker:** Lena Schulz

---

## Agenda

1. Q2 planning status
2. Headcount update
3. Cross-squad dependencies
4. QBR prep
5. Workshop planning (AI tooling session)

---

## Q2 Planning Status

Sarah kicked off. All squads need finalized Q2 OKRs by April 1. Three squads are ready (Growth, Platform, Marketplace). Two are still finalizing:

- **Spend & Control** — Pieter said the team is 90% there but the Policy Engine v2 timeline depends on the Payments API v3 blocker. He'll know more after his call with the Payments team this week.
  - **Action:** Pieter to confirm Policy Engine v2 timeline to Sarah by March 24.

- **Integrations** — Carmen said her team is waiting on a headcount decision before committing to the SAP integration timeline.
  - **Action:** Sarah to get headcount confirmation from CEO by March 20.

Sarah reminded everyone: Q2 OKRs should be ambitious but achievable. "I'd rather we commit to 3 things and ship all 3 than commit to 5 and ship 2."

## Headcount Update

Sarah shared the latest from the CEO:
- 2 new PM hires approved for H1 (one senior, one mid-level)
- 1 additional designer approved (senior product designer)
- Backfill for the PM who left Growth team last month — approved, recruiting starts this week.

Pieter asked if Spend & Control could get one of the new PMs. His squad has 5 PMs covering too many surfaces. Sarah said she'll consider it but Growth has the stronger case right now (they lost someone).

- **Action:** Pieter to write a 1-pager on why Spend & Control needs a 6th PM. Due March 24.
- **Action:** Erik to share the Growth team PM job description with Sarah for posting this week.

## Cross-Squad Dependencies

Three active cross-squad dependencies flagged:

1. **Payments API v3** (Payments → Spend & Control): Real-time balance check needed for Policy Engine v2. Payments team ETA: April 4, but has slipped twice.
   - **Action:** Pieter to escalate to Payments team lead. If April 4 slips again, Pieter will bring to Sarah for exec escalation.

2. **SSO consolidation** (Platform → All squads): Platform team is migrating to a new SSO provider. All squads need to test their auth flows by April 15.
   - **Action:** Carmen to send testing checklist to all squad leads by March 21.

3. **Analytics migration** (Data team → All squads): Amplitude contract renews April 30. Data team evaluating whether to renew or switch to PostHog. If they switch, all custom dashboards need rebuilding.
   - **Action:** Lena to get a decision from the Data team by March 28 so squads can plan.
   - Rosa raised concern: "If we switch analytics tools mid-quarter, we'll lose continuity on our design metrics. Can we at least export the A/B test history?"

## QBR Prep

QBR is April 1. Each squad presents 15 minutes. Sarah wants:
- 3 slides max per squad
- Lead with customer impact, not feature lists
- Include one honest "what we got wrong" moment

**Action items for QBR:**
- **Pieter:** Pull Spend & Control metrics by March 28 (Marcus already requested — see email thread).
- **Erik:** Growth metrics by March 28. Include the landing page conversion experiment results.
- **Carmen:** Platform metrics by March 28. Include uptime numbers and SSO migration progress.
- **Rosa:** Design team impact slide — time-to-ship improvements, accessibility audit results, design system adoption. By March 28.
- **Lena:** Create the QBR deck template and send to all squad leads by March 19.
  - **Action:** Lena to create QBR template.

## Workshop Planning (AI Tooling Session)

Sarah mentioned that Pieter is working with Every Consulting on an AI workshop for the product and design org. March 27, 3-6 PM CET.

Pieter gave a quick update:
- 75 people invited (full PM + Design org)
- Mix of exercises: guided cross-tool synthesis, solo build time for individual use cases
- Data pack being prepared so people can practice even without MCP connectors
- Every Consulting (Mike Taylor) running it

Sarah: "This is important. I want everyone to attend, not just the early adopters. Send calendar blocks."

Rosa asked if designers would get design-specific exercises. Pieter said yes — the exercise list includes building prototypes and running design critiques with AI.

- **Action:** Pieter to send calendar invites to the full PM + Design org by March 18.
- **Action:** Pieter to share the exercise list with Rosa so she can prep her design team.
- **Action:** Rosa to identify 3-4 TAs from the design team for the workshop.

## Misc

- Lena flagged that the monthly product newsletter is overdue. Last one went out Feb 15.
  - **Action:** Lena to draft and send by March 21.
- Erik mentioned the landing page A/B test results are in — new version has 12% higher conversion. Wants to discuss at the next Growth sync.
- Carmen asked about the Vercel migration timeline. Platform team is evaluating moving the marketing site to Vercel from their current setup. No action needed yet — just flagging.

---

**Next sync: March 31, 2026**
