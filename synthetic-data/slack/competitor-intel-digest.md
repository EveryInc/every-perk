# #competitor-intel — Week of March 10–24, 2026

**Monday, March 10**

**Nurdan Fatoglu** 9:30 AM
FYI — Navan just posted a blog about Ava handling 500K+ queries since January launch. Key stat: "67% of expense categorization queries resolved without human intervention." Not sure how they're measuring "resolved" but the messaging is good.

Link: [redacted — internal competitive tracking only]

**Alex Walker** 9:45 AM
500K queries in 2 months is impressive. That's about 8K/day. Even if half are trivial ("what's my expense status?"), the other half is meaningful.

**Nurdan Fatoglu** 9:50 AM
Also noticed they're pushing hard on the "Navan Rewards" program — employees earn personal travel credits from business bookings. Clever retention play. Several of our customers have mentioned it.

---

**Wednesday, March 12**

**Neil Rogers** 2:00 PM
Interesting G2 review from last week — a Concur customer who switched to Navan:

> "We left Concur after 8 years because the product felt frozen in time. Navan isn't perfect but it feels like a modern tool built for people who actually travel. The AI assistant is useful about 60% of the time."

The "60% useful" note is interesting. That's a low bar we can beat if we ship something more grounded in actual policy data.

**Tudor Tise** 2:15 PM
"60% useful" — that's our opening. If our assistant is grounded in the real policy engine (not just LLM vibes), we could be at 90%+ accuracy for policy queries. That's a meaningful differentiator.

---

**Thursday, March 13**

**Alex Walker** 10:00 AM
Just came out of a deal review. Prospect (650-person fintech) is choosing between Perk and Navan. The deciding factor: "which one has AI expense categorization live today?" Navan wins on that today. They specifically asked when our auto-cat is shipping.

Sales team told them "Q2" — which is technically true for SPEND-142, but tight.

**Pieter Odink** 10:15 AM
This is the third deal in 6 weeks where AI categorization was the deciding factor. @nurdan how confident are we on the April 15 target?

**Nurdan Fatoglu** 10:20 AM
Depends on OCR. If SPEND-148 hits 90% by April 1, we're on track. If not, we can ship with wider manual fallback ranges — less impressive but functional. I'm cautiously optimistic.

---

**Monday, March 17**

**Lydia Foster** 11:00 AM
Ramp just raised $300M at a $13B valuation. Press release is all about AI: "AI-native expense management." Their auto-categorization accuracy claim: 95%. Take with a grain of salt but it's a strong number.

**Nurdan Fatoglu** 11:10 AM
95% for auto-categorization is what we're targeting too, at the "suggest" tier. Our "auto-apply" tier targets 85%. The difference is we're more conservative — we'd rather ask the user to confirm than apply a wrong category. Different philosophy.

**Neil Rogers** 11:15 AM
Ramp's 95% claim is probably on US-only data with USD expenses. Our customer base is 60%+ international. Multi-currency makes everything harder. Would love to see their accuracy on CHF and SEK receipts.

---

**Wednesday, March 19**

**Delia Di Filippantonio** 3:00 PM
Quick competitive note: SAP Concur finally announced "Concur Intelligence" launch date — June 2026. Features listed:
- AI-powered expense categorization
- Predictive spend analytics
- "Smart audit" for compliance
- Natural language search

They're playing catch-up but their install base is massive. Once they ship AI features, the "nobody gets fired for buying Concur" factor gets even stronger.

**Pieter Odink** 3:15 PM
June is 2 months after our target. If we ship AI categorization by April 15, we have a 2-month window where we're the modern-enterprise option with AI AND Concur-level compliance. That's our positioning.

---

**Thursday, March 20**

**Alex Walker** 9:00 AM
Brex just announced integrations with NetSuite, Sage, Xero, Microsoft Dynamics, and FreshBooks. They're going after our mid-market customers who need ERP integration.

We only integrate with SAP (on the roadmap) and Quickbooks (live). The gap is growing.

**Tudor Tise** 9:15 AM
Adding this to the integration roadmap discussion. We might need to accelerate the ERP integration strategy. @pieter should we discuss at the next planning session?

**Pieter Odink** 9:20 AM
Yes. Add it to the April 1 agenda. We can't do everything in Q2 but we need a credible story for prospects who ask about ERP support.

---

**Friday, March 21**

**Nurdan Fatoglu** 4:00 PM
Weekly competitive summary:
- **Navan:** Ava AI at 500K queries, Navan Rewards program gaining traction
- **Brex:** 5 new ERP integrations, "AI-native" positioning with $300M raise
- **SAP Concur:** "Concur Intelligence" launching June 2026
- **Ramp:** $13B valuation, claiming 95% auto-categorization accuracy

**Our position:** We're behind on AI features but our April 15 target for SPEND-142 puts us ahead of Concur. Group Booking v2 is a differentiator nobody else has at our quality. Policy Engine v2 (when unblocked) will be best-in-class for enterprise.

**Biggest risk:** If SPEND-142 slips past April, we lose the window to position as "first enterprise player with AI categorization." Concur ships in June and they have the brand.
