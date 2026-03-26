# Gmail — Recent Stakeholder Threads (Spend & Control)

---

## Thread 1: Group Booking v2 — Launch Update

**From:** Alex Walker <alex.walker@perk.com>
**To:** Sarah Chen (VP Product) <sarah.chen@perk.com>, Pieter Odink <pieter.odink@perk.com>
**Cc:** Spend & Control Squad
**Date:** March 18, 2026 5:45 PM CET
**Subject:** Group Booking v2 — Shipped to 100% ✅

Hi Sarah,

Quick update: Group Booking v2 is now live for all users. The rollout was clean — no incidents, no rollbacks.

Key changes in v2:
- New organizer flow: create trip → invite travelers → collect preferences → auto-bundle
- 3x faster booking completion in internal testing
- Mobile-responsive for the first time

We'll have real metrics by end of week. Early signals from the first few hours look positive. I'll send a proper readout once Agustina has the dashboard up.

Thanks to the whole squad — this was a 6-week push and the team crushed it.

Alex

---

**From:** Sarah Chen <sarah.chen@perk.com>
**Date:** March 18, 2026 6:12 PM CET
**Subject:** Re: Group Booking v2 — Shipped to 100% ✅

Congrats team! This is a big milestone. Looking forward to the metrics readout.

Two questions for the next update:
1. What's our plan for enterprise customers with 20+ person groups? Any performance concerns?
2. Are we tracking impact on support ticket volume?

Great work.

Sarah

---

## Thread 2: Policy Engine v2 — Payments API Dependency

**From:** Neil Rogers <neil.rogers@perk.com>
**To:** Pieter Odink <pieter.odink@perk.com>
**Date:** March 21, 2026 2:45 PM CET
**Subject:** Policy Engine v2 — blocked, need your help

Hi Pieter,

As discussed in today's sync, Policy Engine v2 is blocked on the Payments API v3 real-time balance check endpoint. Without it, we can't enforce spend caps in real time — we'd only be able to check after the fact, which defeats the purpose.

The Payments team's current ETA is April 4, but this has slipped twice already (originally March 14, then March 21). I'm worried about another slip.

Can you escalate? If we don't get this by April 4, we'll miss our Q2 target for Policy Engine. The UI and rule logic will be ready — it's purely the API dependency.

Options if it slips again:
A) Ship with async-only policy checks (check after submission, not before). Weaker but shippable.
B) Wait for the API. Stronger product but we miss the date.
C) Build a lightweight balance cache ourselves. Risky, and the Payments team won't love it.

I'd recommend we commit to option A as the fallback plan now, so we're not scrambling if April 4 slips.

Neil

---

**From:** Pieter Odink <pieter.odink@perk.com>
**Date:** March 21, 2026 3:30 PM CET
**Subject:** Re: Policy Engine v2 — blocked, need your help

Neil — agreed, this needs to escalate. I have a call with Payments team lead tomorrow morning. I'll push for a hard commitment on April 4 and ask for a contingency plan on their side.

Let's go with option A as fallback. Can you spec what "async-only policy checks" looks like so we're ready to pivot fast if needed?

Pieter

---

## Thread 3: Quarterly Business Review — Spend & Control Data Request

**From:** Marcus Weber (CFO) <marcus.weber@perk.com>
**To:** Pieter Odink <pieter.odink@perk.com>
**Cc:** Agustina Di Clemente <agustina.diclemente@perk.com>
**Date:** March 22, 2026 10:00 AM CET
**Subject:** QBR prep — need Spend & Control numbers by March 28

Hi Pieter,

For the quarterly business review on April 1, I need the following from your squad:

1. **Expense submission metrics:** avg time to submit, miscategorization rate, trend over last 3 quarters
2. **Policy compliance:** violation rate by category, top 5 most violated policies, trend
3. **Group booking:** conversion rate (old vs new flow), avg group size, revenue impact estimate
4. **Support tickets:** volume trend, top categories, avg resolution time
5. **Cost savings:** estimated FTE hours saved through automation this quarter

Can Agustina pull these together by March 28? Happy to jump on a call if anything is unclear.

Marcus

---

**From:** Pieter Odink <pieter.odink@perk.com>
**Date:** March 22, 2026 10:30 AM CET
**Subject:** Re: QBR prep — need Spend & Control numbers by March 28

Marcus — will do. Agustina will own the data pull. I'll add context and narrative for the readout.

One note: Group Booking v2 only shipped March 18, so we'll have less than 2 weeks of data. I'll present early signals with a caveat that the full picture will come in the Q3 QBR.

Pieter

---

## Thread 4: Customer Escalation — Enterprise Expense Report Timeouts

**From:** Julia Martinez (Customer Success) <julia.martinez@perk.com>
**To:** Neil Rogers <neil.rogers@perk.com>, Tomas Berger <tomas.berger@perk.com>
**Date:** March 20, 2026 4:20 PM CET
**Subject:** URGENT: GlobalTech Inc experiencing expense report timeouts

Hi team,

GlobalTech Inc (one of our top 10 enterprise accounts, 2,400 active travelers) is reporting that expense reports with 50+ line items are timing out during PDF generation. This has happened 6 times in the past week and their finance team is escalating.

They need this resolved ASAP. Their quarterly close is March 31 and they can't submit reports.

Can someone look at this today?

Julia

---

**From:** Tomas Berger <tomas.berger@perk.com>
**Date:** March 20, 2026 4:45 PM CET
**Subject:** Re: URGENT: GlobalTech Inc experiencing expense report timeouts

Julia — known issue. Lydia shipped a fix for the currency rendering part (SPEND-160) which helped, but the core timeout for large reports needs pagination in the PDF generation step. 

Short-term fix: I've bumped the timeout from 30s to 60s for enterprise accounts. That should unblock GlobalTech for now.

Long-term fix: proper pagination. Will log a ticket for Sprint 25.

Tomas
