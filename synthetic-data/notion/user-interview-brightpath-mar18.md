# User Interview — BrightPath Consulting

**Date:** March 18, 2026
**Interviewer:** Neil Rogers
**Participant:** Robert Chen, Controller & Lisa Huang, Marketing Lead
**Company:** 600 travelers, mid-market plan, $95K ARR
**Recording:** Available in Dovetail (link redacted)

---

## Interview Transcript

**Neil:** Thanks for making time. I know Robert, you've been in touch with us about the policy engine. I want to understand your full compliance workflow and where Perk fits — and doesn't fit.

**Robert:** Thanks Neil. Let me give you the full picture. BrightPath is a consulting firm — 600 people, mostly traveling. Our compliance requirements are strict because we bill clients for travel, so every expense needs to be categorized correctly for client billing AND internal accounting. Two different categorization schemes.

**Neil:** Two categorization schemes? Walk me through that.

**Robert:** Sure. When a consultant submits a meal expense, it needs two categories: one for our internal GL code (like "Meals — Client Entertainment") and one for client billing (like "Client: Acme Corp — Travel Expenses"). Right now, Perk only supports one category per expense. So our finance team manually adds the second category in SAP after export.

**Lisa:** This is a huge pain point. Our finance team spends about 15 hours per week just adding client billing codes to expenses that are already categorized in Perk.

**Neil:** That's significant. Multi-category support is something we've heard about but haven't scoped. Let me note that.

**Robert:** On the policy side — which is why you wanted to talk — our situation is complicated. We have different policies for different roles:
- Partners: up to $500/night hotel, business class for flights over 4 hours
- Senior consultants: up to $300/night hotel, economy only
- Junior consultants: up to $200/night hotel, economy only
- Internal staff: up to $150/night hotel, economy only

And then there are client-specific overrides. If a client is paying for travel, the client's policy applies, not ours.

**Neil:** How does that work with approval chains?

**Robert:** It's a nightmare. If a junior consultant books a $250/night hotel for a client engagement where the client allows up to $350, it should be auto-approved. But Perk's current policy engine only knows about our internal $200 limit, so it flags it. My team then has to manually check whether a client override applies, approve it, and document the justification. For 600 travelers, that's dozens of false-positive policy violations per week.

**Neil:** This is exactly what Policy Engine v2 is designed to solve. Configurable rules with context-aware conditions — including client overrides.

**Robert:** That's music to my ears. When is it shipping?

**Neil:** Target is Q2. We're currently blocked on a dependency — the Payments API for real-time enforcement. But the rule configuration UI and logic are in progress.

**Robert:** I'll believe it when I see it. [laughs] No offense, but I've been waiting for better policy support since we onboarded 18 months ago.

**Neil:** Fair point. Let me ask about the approval rules bug you reported. We identified the root cause — a logic error in how AND conditions are evaluated. Fix is being deployed this week.

**Robert:** Good. That bug was a compliance risk for us. Three expenses totaling over $10,000 bypassed our approval chain. If our auditors had caught that before I did, it would have been a finding.

**Neil:** I understand the severity. Can I ask — what would your ideal policy engine look like?

**Robert:** A few things:
1. **Role-based rules** with inheritance. Set a base policy, then override at the role level.
2. **Client-context rules.** If the expense is billable to a client, apply the client's policy.
3. **Cascading approvals.** Under $500: auto-approve. $500-$2,000: manager approval. Over $2,000: manager + finance. Over $5,000: manager + finance + partner.
4. **Real-time enforcement.** Don't let someone book a $400/night hotel if their policy says $200. Block it before the booking, not after.
5. **Clear violation messages.** Tell the person exactly which policy they violated, what the limit is, and who can approve an exception.

**Lisa:** I'd add: **reporting.** I want to see a dashboard that shows policy violations by team, by category, and by client. Right now I have to pull CSV exports and build pivot tables manually.

**Neil:** All of those are in scope for v2 except client-context rules — that's a great idea but probably v3. Everything else — role-based rules, cascading approvals, real-time enforcement, clear messaging, and reporting — we're building.

**Robert:** If you ship even half of that list, you'll make our compliance team very happy.

---

## Key Takeaways

1. **Multi-category expenses** (GL code + client billing code) are a major unmet need for consulting firms. Perk only supports one category — finance teams manually add the second.
2. **Client-context policy overrides** are a must-have for B2B services companies. Current policy engine doesn't account for client-specific rules.
3. **Cascading approval chains** with amount-based thresholds are the expected standard. Current flat approval structure doesn't scale.
4. **Policy violation messages** need to cite the specific policy, threshold, and exception path.
5. **Compliance risk** from the approval bug (SPEND-163) was real — $10K+ bypassed approval. Customer auditors could have flagged this.
6. **Reporting dashboard** for policy violations by team/category/client is a strong request.

## Quotes to Use

> "My team spends 15 hours per week just adding client billing codes to expenses that are already categorized in Perk."

> "If a client is paying for travel, the client's policy applies, not ours. Perk doesn't know the difference."

> "Three expenses totaling over $10,000 bypassed our approval chain. If our auditors had caught that before I did, it would have been a finding."

> "Tell the person exactly which policy they violated, what the limit is, and who can approve an exception."

## Follow-ups

- **Action:** Neil to add "client-context policy rules" to the Policy Engine v3 backlog.
- **Action:** Neil to share the multi-category feature request with Nurdan (potential auto-categorization implication).
- **Action:** Neil to confirm SPEND-163 fix is verified against BrightPath's account config.
- **Action:** Agustina to scope a policy violation reporting dashboard (fits with QBR data request from Marcus).
