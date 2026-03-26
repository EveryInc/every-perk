# Gmail — Customer Escalation Threads (Q1 2026)

---

## Thread 1: GlobalTech Inc — Expense Report Performance

**From:** Susan Park <susan.park@globaltech.com>
**To:** julia.martinez@perk.com
**Cc:** pieter.odink@perk.com, wei.liu@globaltech.com
**Date:** March 20, 2026 5:30 PM CET
**Subject:** RE: RE: RE: Expense report timeouts — still not resolved

Julia,

I appreciate the quick response yesterday but I need to be direct: this is the fourth time we've raised this issue since February. Every time we're told it's being worked on, but it's still happening.

Our quarterly close is March 31. I have 12 expense reports with 50-80 line items each that literally cannot be submitted through your platform. My team has been manually splitting reports into smaller batches as a workaround, which defeats the purpose of having an expense management tool.

Here are the specific failures from this week:
- March 18: Report #EXP-29441 (67 items) — timeout after 45 seconds
- March 18: Report #EXP-29443 (82 items) — timeout after 52 seconds
- March 19: Report #EXP-29447 (54 items) — succeeded on third attempt after 3 minutes
- March 20: Report #EXP-29451 (71 items) — timeout, still failing

We are a $380K/year customer with 2,400 travelers. I need either:
1. A guaranteed fix date before March 31, or
2. A manual workaround where your team processes these reports on our behalf

I'm looping in Wei (our VP Operations) for visibility.

Best,
Susan Park
Finance Director, GlobalTech Inc

---

**From:** Pieter Odink <pieter.odink@perk.com>
**Date:** March 21, 2026 9:00 AM CET
**Subject:** RE: RE: RE: RE: Expense report timeouts — still not resolved

Susan,

I'm personally taking ownership of this. You're right that this has gone on too long and I apologize for the repeated delays.

Here's what we're doing:
1. **Immediate (today):** We've increased the timeout threshold for your account specifically. This should unblock reports up to ~70 line items. Engineering is deploying this within the hour.
2. **This week:** Our engineering lead Tomas is building pagination for the PDF generation step, which is the root cause. We expect this to fully resolve the issue for any report size.
3. **I will personally email you** on Friday March 28 with confirmation that the fix is deployed and verified against your stuck reports.

If any of your currently blocked reports are still failing after today's hotfix, please reply here and we'll process them manually.

This is our top priority.

Pieter Odink
Group PM Lead, Spend & Control

---

## Thread 2: Meridian Systems — Competitive Evaluation

**From:** Daniel Fischer <daniel.f@meridiansystems.com>
**To:** julia.martinez@perk.com
**Date:** March 15, 2026 3:00 PM CET
**Subject:** Honest feedback before our renewal review

Julia,

We have our vendor renewal review coming up April 15 and I want to give you a heads up on where we stand.

I've been a Perk champion internally since we onboarded 2 years ago, but my team is getting frustrated with the manual expense categorization. We submit around 1,200 expenses per month across 1,800 travelers. Manually categorizing each one is a real productivity drain.

I know auto-categorization is coming (saw the beta badge in the app) but I need to be able to tell my CFO a credible ship date. Our CEO saw a Navan demo last week and asked me why we're not using that instead. Their auto-categorization is already live.

Can you confirm:
1. Is auto-categorization shipping before our renewal review (April 15)?
2. What accuracy can we expect?
3. Will it handle multi-currency receipts? We operate in 8 countries.

I want to renew with Perk. But I need ammunition for my internal review.

Best,
Daniel Fischer
Sales Director, Meridian Systems

---

**From:** Julia Martinez <julia.martinez@perk.com>
**Date:** March 15, 2026 4:30 PM CET
**Subject:** RE: Honest feedback before our renewal review

Hi Daniel,

Thank you for the transparency — this is exactly the kind of feedback that helps us prioritize.

I've flagged this with our product team. Here's what I can share:
- Auto-categorization is in active development with a target of April 15 for initial rollout
- Expected accuracy is 82%+ for auto-apply, 94%+ for suggestions
- Multi-currency support is a core part of the feature (our OCR team is actively improving this)

I want to get you a more precise answer on timing. Would you be open to a 20-minute call with Nurdan (our PM for this feature) next week? She can walk you through the roadmap and timeline.

We value the partnership and I want to make sure you have what you need for your renewal review.

Best,
Julia

---

## Thread 3: BrightPath Consulting — Feature Request: SAP Integration

**From:** Lisa Huang <lisa.h@brightpath.io>
**To:** julia.martinez@perk.com
**Date:** March 12, 2026 11:00 AM CET
**Subject:** SAP integration — any update?

Julia,

Following up on our conversation from the advisory board session. We're implementing SAP S/4HANA for our finance stack and need expense data flowing directly from Perk into SAP.

Currently our finance team exports CSVs from Perk weekly and manually imports them. For 600 travelers generating ~3,000 expenses/month, that's a lot of manual work.

We were told at the advisory board that direct SAP integration was "on the roadmap." Can you share any more detail on timing?

Also — unrelated, but kudos on the group booking update. Carla used it for our sales offsite last week and was raving about it.

Thanks,
Lisa Huang
Marketing Lead, BrightPath Consulting

---

**From:** Julia Martinez <julia.martinez@perk.com>
**Date:** March 12, 2026 2:00 PM CET
**Subject:** RE: SAP integration — any update?

Lisa,

Great to hear about the group booking win!

On SAP: it's on our H2 2026 roadmap. The integration will be bidirectional — expense data from Perk → SAP, and cost centers / GL codes from SAP → Perk. We're scoping the technical requirements this quarter.

I'll make sure you're in the beta program when we're ready for early access (likely late Q3).

Glad Carla had a great experience with group booking — I've asked if she'd be willing to provide a quote for a case study. Would that be okay?

Julia

---

## Thread 4: Apex Dynamics — Policy Engine Bug Report

**From:** Robert Chen <robert.c@apexdynamics.com>
**To:** neil.rogers@perk.com, julia.martinez@perk.com
**Date:** March 19, 2026 9:45 AM CET
**Subject:** Approval rules not triggering — this is becoming a compliance risk

Neil,

I need to escalate this. We've reported three times (tickets ZD-8601, ZD-8712, ZD-8834) that our approval rules are not firing consistently. Last week, a $4,200 hotel expense bypassed our two-level approval chain entirely. I only caught it during manual review.

Our company policy requires manager + finance approval for any expense over $2,000. If Perk's system can't enforce this reliably, we have a compliance gap.

I've documented the specific cases:
- Feb 28: $3,100 flight, policy required approval, auto-approved
- March 7: $2,800 hotel, policy required approval, auto-approved
- March 14: $4,200 hotel, policy required approval, auto-approved

All three had rules configured correctly (I triple-checked with your support team).

What's your plan to fix this? I need an answer before our compliance audit on April 10.

Robert Chen
Controller, Apex Dynamics

---

**From:** Neil Rogers <neil.rogers@perk.com>
**Date:** March 20, 2026 10:30 AM CET
**Subject:** RE: Approval rules not triggering — this is becoming a compliance risk

Robert,

Thank you for the detailed report. I found the root cause.

Your approval rules use AND conditions across two policy groups (the department-based group and the amount-based group). There was a bug in our evaluation engine where it short-circuits if the first policy group returns "no match" — it never evaluates the second group. This means the amount-based approval rule was being skipped entirely.

We've filed this as SPEND-163 (Critical). Tomas is writing the fix now and it will be deployed by end of this week. I'll personally verify against your account configuration before marking it resolved.

For the three expenses that bypassed approval: I recommend flagging them for retroactive review in your system. On our side, we've manually marked them as "policy exception — system bug" so they're visible in your compliance report.

I'm sorry this took three reports to get to the bottom of. We should have caught it sooner.

Neil Rogers
Senior PM, Policy & Compliance
