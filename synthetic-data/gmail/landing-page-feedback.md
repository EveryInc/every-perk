# Gmail — Landing Page Feedback Thread

---

## Thread: Smart Expenses landing page — feedback round

**From:** Erik Lindqvist <erik.lindqvist@perk.com>
**To:** Pieter Odink <pieter.odink@perk.com>, Nurdan Fatoglu <nurdan.fatoglu@perk.com>, Marina Rybalko <marina.rybalko@perk.com>
**Cc:** Sarah Chen <sarah.chen@perk.com>
**Date:** March 23, 2026 10:00 AM CET
**Subject:** Smart Expenses landing page — ready for feedback

Team,

The landing page copy for perk.com/smart-expenses is ready for review (Notion → Landing Page Copy — Smart Expenses). This goes live April 8, same day as the feature launch.

Key decisions I need:
1. The hero stat says "85%+ accuracy" — Nurdan, is this defensible?
2. Susan Park quote — Julia, do we have permission?
3. SOC 2 badge — include or remove?
4. Model isolation language — Nurdan flagged this might overstate our architecture
5. AI Travel Assistant teaser — Tudor wants it, I think it's premature

Please review by March 26 so Marina can start on visuals.

Erik

---

**From:** Nurdan Fatoglu <nurdan.fatoglu@perk.com>
**Date:** March 23, 2026 11:30 AM CET
**Subject:** RE: Smart Expenses landing page — ready for feedback

Erik,

Reviewed. A few concerns:

1. **"85%+ accuracy"** — The model is at 82% in our test set today. I'm confident we'll hit 85% with the final training round (I'm running it this week), but I wouldn't put "85%+" in marketing copy until we've actually measured it post-launch. Suggestion: say "80%+ accuracy at launch, improving over time as the system learns your spending patterns." More honest, and the "improving over time" angle is actually a stronger selling point.

2. **"Model isolation"** — The copy says "your company's data trains YOUR model." This is not accurate today. We use a shared model with per-customer fine-tuning layer. The base model is trained on anonymized aggregate data across all customers. Each customer's override data fine-tunes a thin adaptation layer. To say "your data trains your model" is misleading. Suggestion: "Your company's override data personalizes your categorization over time" — accurate and still compelling.

3. **"Data sovereignty — your expense data never leaves your region"** — This is true for EU customers on the EU data center, but our US customers' data lives in AWS us-east-1 which also processes some non-US customer data during failover. The "never leaves your region" claim is aspirational, not current. I'd remove it or add "for EU-hosted customers."

4. **"10x fewer miscategorized expenses"** — Where does this stat come from? Our target is reducing miscategorization from 23% to under 10% — that's roughly 2x improvement, not 10x. Erik, did you mean "10% miscategorization" not "10x fewer"? Big difference.

These aren't nitpicks — the last thing we want is a customer citing our marketing in a contract dispute because our AI didn't perform as advertised.

Nurdan

---

**From:** Erik Lindqvist <erik.lindqvist@perk.com>
**Date:** March 23, 2026 12:00 PM CET
**Subject:** RE: RE: Smart Expenses landing page — ready for feedback

Nurdan,

Fair points, especially #4 — that was my math error. 23% to 10% is a ~2x improvement, not 10x. I'll fix.

On #1: I still think "85%" is a stronger headline than "80%+". Can we compromise with "up to 85% accuracy" or "85% target accuracy"? The qualifier gives us room while keeping the number.

On #2 and #3: Agreed. I'll revise both.

Updated copy coming today.

---

**From:** Pieter Odink <pieter.odink@perk.com>
**Date:** March 23, 2026 2:00 PM CET
**Subject:** RE: RE: RE: Smart Expenses landing page — ready for feedback

Erik, Nurdan,

I want to weigh in on the accuracy framing. Nurdan is right — we should not overstate. But Erik is also right that "85%" is a stronger marketing message.

**My call:** Launch the page with "up to 85% accuracy" with a footnote: "Based on internal testing as of April 2026. Accuracy improves over time as the system learns your company's spending patterns." This is defensible, aspirational, and honest.

On the other items:
- SOC 2 badge: **remove**. Don't advertise what we don't have.
- AI Travel Assistant teaser: **no**. Don't announce what we haven't committed to shipping.
- Susan Park quote: I'll follow up with Julia. If we don't have permission by April 4, use an anonymized quote.
- Model isolation: use Nurdan's revised language.
- Data sovereignty: restrict to "EU data residency available for EU customers."

**One more thing:** The landing page doesn't address Persona 4 ("Compliance Carl") at all. The "Enterprise Ready" section touches on audit trails but doesn't mention configurable policy rules, approval chains, or compliance reporting. These are top-3 buying criteria for our enterprise segment. Can you add a subsection?

Also — I think the page is missing a comparison angle. CFOs compare tools. Even if we don't name competitors, we should have a "Why Perk" section that implicitly addresses the Concur-is-clunky and Navan-is-not-enterprise-ready positioning.

Pieter

---

**From:** Marina Rybalko <marina.rybalko@perk.com>
**Date:** March 23, 2026 3:30 PM CET
**Subject:** RE: RE: RE: RE: Smart Expenses landing page — ready for feedback

Quick design notes:

- The hero animation concept (split screen: old way vs. new way) is great. I can build this in Figma + Rive for the actual implementation. Need 3 days after copy is finalized.
- The stat blocks section needs visual hierarchy. "85%+" should be the dominant number — 72px, bold, brand color. The others can be smaller.
- I want to propose a real-time demo widget in the page — a fake receipt image where you can click "Categorize" and see the AI assign a category in real time. Similar to what Stripe does with their API demo on the homepage. Would take ~1 week of eng time.
- Typeface: Geist Sans for headlines, Geist Mono for the stat numbers. Consistent with our brand.

One concern: the page is copy-heavy. I'd recommend cutting 30% of the body text and letting visuals do more work. Travelers don't read walls of text on a landing page — they scan.

Let me know when copy is final and I'll start.

Marina
