# #spend-control — Week of March 18–24, 2026

**Monday, March 18**

**Alex Walker** 10:02 AM
🚀 Group Booking v2 is live to 100%. Rollout went clean, no incidents. Dashboard coming this week from Agustina. Let's see how the numbers look.

**Pieter Odink** 10:15 AM
Great work Alex and the whole team. This was a big one. Let's keep a close eye on support tickets this week.

**Marina Rybalko** 10:22 AM
The design team is proud of this one. Shoutout to the eng team for nailing the traveler preference step — that was tricky.

---

**Tuesday, March 19**

**Tudor Tise** 9:45 AM
Slack bot question: should the weekly spend summary go to #finance-leads only, or should squad leads also get a version in their own channels? Thinking about opt-in per channel.

**Neil Rogers** 10:01 AM
Start with #finance-leads. We can expand once we know people actually read it. Let's not over-engineer this.

**Tudor Tise** 10:03 AM
Fair. Keeping it simple.

---

**Wednesday, March 20**

**Nurdan Fatoglu** 11:30 AM
OCR update: Tomas got multi-currency extraction to 81% accuracy. Still not at 90% target but solid progress. Biggest remaining gap is handwritten receipts from German/Austrian hotels — those are tough.

**Tomas Berger** 11:35 AM
Yeah the handwritten ones are a pain. Going to try a different preprocessing pipeline this week. Should get us to 85%+ at least.

**Nurdan Fatoglu** 11:37 AM
That would unblock us for the "suggest" tier at least. We could ship with a wider manual fallback range for the rest.

---

**Thursday, March 21**

**Neil Rogers** 2:15 PM
Policy Engine v2 is still blocked on Payments API v3. I've asked Pieter to escalate. In the meantime, Marina and I are using the time to polish the rule builder UI. Silver lining: the UI is going to be really clean.

**Pieter Odink** 2:30 PM
I have a call with the Payments team lead tomorrow. Will push for a firm date.

**Mauro Spadaro** 3:00 PM
Starting on the notification spec for approval chains (SPEND-157). Question: do we want Slack-only notifications for approvals, or email + Slack? I'd vote both with a preference setting.

**Neil Rogers** 3:05 PM
Both. Approvals are too important to be Slack-only. Some managers live in email.

---

**Friday, March 22**

**Agustina Di Clemente** 9:15 AM
Group booking numbers through day 4: 847 group bookings created, 68% conversion rate. Biggest drop-off is the traveler preference step at 32% abandon. Could be UX or could be travelers who were invited but aren't interested.

**Alex Walker** 9:20 AM
I think it's a mix of both. Going to dig into the data next week. The 14 mixed cabin class tickets are annoying but low priority — SPEND-120 is logged for Sprint 25.

**Lydia Foster** 11:00 AM
PDF export fix (SPEND-160) is deployed. No more garbled £ and € symbols. Small win but our finance users will notice.

**Pieter Odink** 4:45 PM
Good week team. Quick summary for my LT update:
- Group Booking v2 shipped, early numbers look strong
- Smart Expense Categorization on track, OCR improving
- Policy Engine blocked on Payments API — I'm escalating
- Slack bot and reporting fixes moving along

Have a good weekend everyone.
