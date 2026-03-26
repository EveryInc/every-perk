# Dashboard Requirements — Spend & Control Squad KPIs

**From:** Pieter Odink
**To:** Agustina Di Clemente
**Date:** March 19, 2026
**Context:** Follow-up from the Marcus QBR data request and our ongoing need for a single source of truth.

---

## The Problem

We don't have a single dashboard. Metrics are scattered across:
- Amplitude (product usage, funnels)
- Looker (financial data, revenue metrics)
- Zendesk (support tickets)
- Backend SQL queries (custom calculations)
- Spreadsheets (Agustina's manual pulls)

This means every time someone asks "how are we doing?" — QBR, board meeting, weekly sync — we scramble for 2-3 days pulling data from 5 sources. That's not sustainable.

The Amplitude vs. backend discrepancy on group booking conversion (68% vs 64%) is a symptom of this problem. We're reporting different numbers depending on which tool we use.

## What I Want

A single internal dashboard that shows:

### Section 1: Health Metrics (Real-time or Daily Refresh)
- Active travelers (total count, trend)
- Expense submission volume (daily, weekly)
- Support ticket volume (daily, by category)
- System performance (PDF generation times, OCR processing times, API latency)

### Section 2: Product Metrics (Weekly Refresh)
- Avg expense submission time (mean + median)
- Miscategorization rate (overall + by category)
- Group booking conversion rate (funnel with step-by-step drop-off)
- Policy violation rate (by category, by team size)
- OCR accuracy (overall + by currency)
- CSAT score (with response rate)

### Section 3: Business Metrics (Monthly Refresh)
- Revenue by feature area
- Customer retention rate
- Support cost per ticket
- Estimated FTE hours saved through automation

### Section 4: Initiative Trackers
- **SPEND-142 (AI Categorization):** Model accuracy over time, % of expenses auto-categorized (once launched)
- **SPEND-118 (Group Booking v2):** Post-launch conversion, satisfaction, support tickets
- **SPEND-155 (Policy Engine v2):** Blocked — show dependency status and ETA
- **SPEND-161 (Slack Bot):** Adoption metrics (channels active, messages sent)

## Requirements

1. **Single URL** that I can share with Sarah, Marcus, and the team.
2. **Date range picker** — default to last 30 days, but support custom ranges.
3. **Comparison mode** — show current period vs. previous period (WoW or MoM).
4. **Export** — CSV export for any chart or table.
5. **Mobile-friendly** — I check metrics on my phone.
6. **Access control** — Team can view, only Agustina and I can edit.

## Data Source Reconciliation

Before building the dashboard, we MUST reconcile the known discrepancies:
- Group booking conversion: Amplitude (68%) vs. backend (64%) — which is the source of truth?
- OCR accuracy: Tomas's weekly sample (81%) vs. Amplitude event tracking (78%) — different measurement methods?
- Support tickets: Zendesk tags are inconsistent. Some tickets tagged "expenses" should be "booking." Need a tagging audit.

**Action:** Agustina to document the reconciliation decisions and establish the canonical data source for each metric.

## Timeline

- **Phase 1 (March 28):** Health metrics + product metrics. Minimum viable dashboard for QBR prep.
- **Phase 2 (April 15):** Business metrics + initiative trackers. Full dashboard.
- **Phase 3 (May):** Alerts (Slack notification when key metrics move >10% WoW).

## Tool Suggestion

I'd prefer Looker since we already use it for finance data. But if Amplitude's dashboard builder is easier for the product metrics, use that. Just don't make me log into 3 different tools.

Actually — has anyone evaluated Retool or Hex? Might be worth a quick look if they can pull from multiple data sources into one view.
