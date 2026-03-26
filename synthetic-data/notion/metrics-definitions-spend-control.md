# Metrics Definitions — Spend & Control Squad

**Owner:** Agustina Di Clemente
**Last updated:** March 15, 2026

---

## North Star Metric

**Time-to-reconciliation (TTR):** The elapsed time from when an employee submits an expense to when the finance team marks it as reconciled. Lower is better. Current: 6.8 days. Target: 3 days by end of Q2.

---

## Primary Metrics

### 1. Expense Submission Time
**Definition:** Average time (in seconds) from opening the "New Expense" form to successful submission.
**Source:** Backend event logs (`expense.submission.started` → `expense.submission.completed`)
**Current:** 252 seconds (4m 12s)
**Target:** 150 seconds (2m 30s) by end of Q2
**Owner:** Nurdan Fatoglu
**Notes:** This metric is inflated by power users who submit 30+ items in one session. Median is 180 seconds. Consider switching to median.

### 2. Expense Miscategorization Rate
**Definition:** Percentage of expense line items where the category was changed after initial submission (by either the submitter or the finance reviewer).
**Source:** Backend event logs (`expense.category.changed` / total `expense.submitted`)
**Current:** 23%
**Target:** Under 10% by end of Q2
**Owner:** Nurdan Fatoglu
**Notes:** This metric will be the primary success indicator for Smart Expense Categorization (SPEND-142). Baseline measured over the 90 days before feature launch.

### 3. Group Booking Conversion Rate
**Definition:** Percentage of initiated group bookings that result in a completed booking (all travelers confirmed, payment processed).
**Source:** Amplitude event funnel: `group_booking.started` → `group_booking.completed`
**Current:** 68% (post-v2 launch, Amplitude) / **64%** per backend calculation
**Target:** 75% by end of Q2
**Owner:** Alex Walker
**⚠️ DISCREPANCY NOTE (March 22):** Amplitude shows 68% but the backend SQL query returns 64%. Agustina is investigating. Likely cause: Amplitude excludes users who enter the flow via deep links (no `page_view` event fires before `group_booking.started`). The backend counts all funnel entries regardless of entry point. **Use backend number (64%) until reconciled.**

### 4. Policy Violation Rate
**Definition:** Percentage of submitted expenses that trigger at least one policy violation.
**Source:** Backend event logs (`policy.violation.triggered` / total `expense.submitted`)
**Current:** 8.4%
**Target:** Under 5% by end of Q3 (requires Policy Engine v2 with better upfront prevention)
**Owner:** Neil Rogers
**Notes:** This metric should *increase* temporarily when Policy Engine v2 launches (more rules catching more violations), then *decrease* as employees learn the new rules.

### 5. Traveler Satisfaction (CSAT)
**Definition:** Post-trip survey score (1-5 scale). Sent 48 hours after trip completion.
**Source:** SurveyMonkey (auto-triggered by `trip.completed` event)
**Current:** 4.1 / 5.0
**Target:** 4.3 / 5.0 by end of Q2
**Owner:** Alex Walker
**Notes:** Response rate is 22%. Consider incentivizing to increase. Low response rate means small sample bias.

### 6. Support Ticket Volume (Spend-Related)
**Definition:** Weekly count of Zendesk tickets tagged with any "spend-" category.
**Source:** Zendesk API export
**Current:** 342/week
**Target:** Under 250/week by end of Q2
**Owner:** Pieter Odink (overall), individual PMs for their categories
**Notes:** The timeout tickets (GlobalTech) are inflating the number. Removing those, volume is ~310/week.

---

## Secondary Metrics

### 7. OCR Accuracy
**Definition:** Percentage of receipt fields (merchant, amount, currency, date) correctly extracted by the OCR pipeline.
**Source:** Human-reviewed sample of 200 receipts per week
**Current:** 81% overall / 91% for EUR / 68% for multi-currency
**Target:** 90% overall by April 1
**Owner:** Tomas Berger

### 8. Approval Chain Completion Time
**Definition:** Average time from expense submission to final approval (for expenses requiring approval).
**Source:** Backend event logs (`expense.submitted` → `expense.approved`)
**Current:** 2.3 days
**Target:** 1 day by end of Q3 (requires SPEND-157 notifications)
**Owner:** Mauro Spadaro

### 9. Mobile vs. Desktop Submission Split
**Definition:** Percentage of expenses submitted via mobile app vs. desktop.
**Source:** Backend event logs (client_platform field)
**Current:** 38% mobile / 62% desktop
**Trend:** Mobile share increasing ~2% per month
**Owner:** Tomas Berger
**Notes:** Mobile submissions have 30% higher OCR error rate due to photo quality. SPEND-162 (auto-crop) should help.

### 10. Revenue per Feature
**Definition:** Estimated ARR attributable to each major feature (based on sales team attribution in Salesforce).
**Source:** Salesforce deal attribution field (manual, inconsistent)
**Current estimates:**
- Expense management (core): 45% of ARR
- Travel booking: 30% of ARR
- Policy & compliance: 15% of ARR
- Reporting & analytics: 10% of ARR
**Owner:** Erik Lindqvist (Growth)
**Notes:** These estimates are rough. Sales team attribution is inconsistent (~60% fill rate). Take with a grain of salt.

---

## Dashboard Access

- **Amplitude:** Main product analytics dashboard → "Spend & Control — Q2 2026"
- **Looker:** Finance metrics → "Spend Squad — Operational"
- **Zendesk:** Support metrics → "Spend Category Analysis"
- **Internal dashboard (WIP):** Agustina building SPEND-119, expected end of Sprint 24
