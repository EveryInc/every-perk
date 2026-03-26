# Competitive Landscape — Travel & Expense Management

**Owner:** Nurdan Fatoglu (with input from Alex Walker, Neil Rogers)
**Last updated:** March 10, 2026
**Status:** Living document — updated monthly

---

## Overview

Perk operates in the corporate travel and expense management space. The market is consolidating around platforms that combine booking, expense management, and policy compliance into a single product. AI is becoming a key differentiator.

---

## Primary Competitors

### 1. Navan (formerly TripActions)

**Positioning:** "The all-in-one travel, expense, and card platform"
**Estimated ARR:** $500M+ (public sources)
**Key customers:** Figma, GitHub, Lyft, Dropbox

**Strengths:**
- **Ava AI Assistant** (launched Jan 2026) — conversational booking and expense queries via Slack and in-app. Mixed reviews but the market positioning is strong.
- Mobile-first experience — their app is fast. Receipt capture uses on-device ML for preprocessing. Multiple customers have cited Navan's mobile speed as a differentiator.
- Virtual corporate cards with real-time spend controls — this is where they're strongest.
- Strong self-serve onboarding — mid-market companies can go live in under a week.

**Weaknesses:**
- Enterprise features are thin. Large accounts (2,000+ travelers) report performance issues and missing compliance features.
- Customer support has declined since rapid scaling — Glassdoor reviews mention support as a pain point.
- Pricing is opaque. No public pricing page. Multiple customers report unexpected fee increases at renewal.
- Ava AI is hit-or-miss for complex queries. Works well for "book me a flight to X" but struggles with multi-leg trips and policy exceptions.

**Recent moves:**
- Jan 2026: Launched Ava AI assistant
- Feb 2026: Acquired a small OCR startup (name unknown) — likely to improve receipt processing
- Mar 2026: Announced "Navan Rewards" — personal travel rewards for business travelers

**Perk comparison:**
| Feature | Perk | Navan |
|---------|------|-------|
| Group booking | ✅ v2 shipped | ✅ Basic |
| AI categorization | 🔄 In progress (Apr target) | ✅ Live |
| AI assistant | 📋 Exploring | ✅ Ava (Jan 2026) |
| Policy engine | 🔄 v2 in progress | ✅ Basic rules |
| Mobile receipt OCR | 🔄 Improving (81%) | ✅ Strong (on-device) |
| Enterprise scale | ✅ Strong | ⚠️ Growing pains |
| SAP integration | 📋 H2 2026 roadmap | ✅ Available |

---

### 2. SAP Concur

**Positioning:** "The world's leading travel, expense, and invoice management solution"
**Estimated ARR:** $2B+ (SAP subsidiary)
**Key customers:** Most Fortune 500 companies

**Strengths:**
- Dominant in enterprise. Deeply integrated with SAP ERP.
- Compliance and audit features are best-in-class. SOX compliance, multi-entity support, intercompany billing.
- Global coverage — supports 200+ countries, all major currencies, local tax rules.
- "Nobody gets fired for buying Concur" — brand trust with procurement teams.

**Weaknesses:**
- User experience is dated. The UI hasn't had a major refresh since 2019. Frequent complaints about the mobile app.
- Innovation pace is slow. Their "ConcurBot" (Slack integration) is barely functional — limited to expense status lookups.
- Implementation is heavy — enterprise onboarding takes 3-6 months and requires SI partners.
- Pricing is expensive. Per-transaction fees add up for high-volume customers.
- No AI categorization or predictive features. All manual.

**Recent moves:**
- Oct 2025: Announced "Concur Intelligence" — AI features coming in 2026, no ship date.
- Jan 2026: New mobile app redesign (incremental improvement, not transformative).
- No major acquisitions or AI announcements.

**Perk comparison:**
| Feature | Perk | SAP Concur |
|---------|------|------------|
| Group booking | ✅ v2 shipped | ⚠️ Complex, via agency |
| AI categorization | 🔄 In progress | ❌ Manual only |
| AI assistant | 📋 Exploring | ⚠️ Basic "ConcurBot" |
| Policy engine | 🔄 v2 in progress | ✅ Enterprise-grade |
| Mobile receipt OCR | 🔄 Improving | ✅ Functional but dated |
| Enterprise scale | ✅ Strong | ✅ Best-in-class |
| SAP integration | 📋 H2 2026 roadmap | ✅ Native |

---

### 3. Brex

**Positioning:** "AI-powered spend platform"
**Estimated ARR:** $300M+ (estimates)
**Key customers:** DoorDash, Coinbase, Indeed, Scale AI

**Strengths:**
- **AI-first approach.** Auto-categorization, receipt matching, and policy checking are all AI-powered. They shipped this before anyone else in the space.
- Corporate card + expense in one product. No need for separate card and expense tools.
- Developer-friendly API. Strong partner ecosystem.
- Real-time spend visibility with budget alerts.

**Weaknesses:**
- Travel booking is basic. They partner with third parties — not a native travel product.
- International support is limited compared to Perk and Concur.
- Mid-market focused. Enterprise customers with complex multi-entity structures find Brex too simple.
- No group booking capability.

**Recent moves:**
- Feb 2026: Launched "Brex Intelligence" — analytics dashboard with spend predictions.
- Mar 2026: Announced integration with 5 new ERP systems (NetSuite, Sage, etc.)

**Perk comparison:**
| Feature | Perk | Brex |
|---------|------|------|
| Group booking | ✅ v2 shipped | ❌ No travel booking |
| AI categorization | 🔄 In progress | ✅ Live (strong) |
| AI assistant | 📋 Exploring | ❌ Not available |
| Policy engine | 🔄 v2 in progress | ✅ AI-powered |
| Corporate cards | ❌ Partner only | ✅ Native |
| International | ✅ 80+ countries | ⚠️ Limited |

---

### 4. Ramp

**Positioning:** "The ultimate platform for finance teams"
**Estimated ARR:** $200M+ (estimates)
**Key customers:** Shopify, Notion, Anduril

**Strengths:**
- Best-in-class UX. Consistently wins design awards.
- Fast-growing with strong product velocity.
- AI receipt matching and categorization — very accurate.
- Price intelligence — alerts when you're overpaying for software subscriptions.

**Weaknesses:**
- US-focused. International support is a work in progress.
- No travel booking. Pure expense and card management.
- Not suitable for complex enterprise compliance requirements.

**Recent moves:**
- Jan 2026: Launched AI-powered "memo drafts" — auto-generates expense justifications.
- Mar 2026: Raised $300M Series E at $13B valuation.

---

## Competitive Positioning Summary

```
                    Enterprise Complexity →
                    Low                    High
                ┌─────────────────┬─────────────────┐
    AI/Modern   │                 │                  │
    Experience  │   Ramp          │   ← GOAL FOR     │
        ↑       │   Brex          │     PERK H2 2026 │
        High    │                 │                  │
                ├─────────────────┼─────────────────┤
                │                 │                  │
        Low     │   Legacy tools  │   SAP Concur     │
                │   (Expensify    │                  │
                │    Certify)     │                  │
                └─────────────────┴─────────────────┘
```

Perk's strategic position: **modern UX + enterprise capability.** We need to match Navan/Brex on AI features while keeping our enterprise strength.

---

## Key Competitive Gaps (Action Required)

1. **AI categorization** — Navan and Brex both have this. We're behind. SPEND-142 is critical.
2. **AI assistant** — Navan's Ava is first-mover. We need a response in 2026.
3. **Mobile speed** — Navan's on-device ML approach is faster than our server-side OCR. Need to close the gap.
4. **SAP integration** — Concur's native advantage. Our H2 roadmap item is the right priority.
5. **Corporate cards** — Both Brex and Ramp are card-first. We use partner cards. Not a 2026 priority but a strategic question for 2027.

---

## Sources & Notes

- Navan info: from customer feedback, public press releases, and a trial account one of our sales reps set up.
- SAP Concur: from G2 reviews, Gartner MQ, and customer comparisons.
- Brex/Ramp: from press releases, public pricing pages, and demo recordings.
- **NOTE:** This doc needs updating after the Gartner MQ for T&E Management releases (expected April 2026). Last year Perk was a "Niche Player" — we should target "Visionary" this year.
