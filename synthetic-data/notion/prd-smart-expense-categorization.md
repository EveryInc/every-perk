# PRD: Smart Expense Categorization

**Owner:** Nurdan Fatoglu
**Squad:** Spend & Control
**Status:** In Progress
**Target ship date:** April 15, 2026
**Last updated:** March 22, 2026

---

## Problem

Perk users manually categorize every expense when submitting reports. This takes an average of 12 seconds per line item, and with an average of 14 line items per report, that's nearly 3 minutes of tedious work per submission. Miscategorization rate is 23%, which causes downstream reconciliation issues for finance teams.

## Opportunity

Auto-categorize expenses using ML trained on 18 months of historical categorization data across 10,000+ Perk customers. Early model testing shows 82% accuracy at the "auto-apply" confidence level and 94% accuracy at the "suggest" level.

## Solution

When a user submits a receipt or adds an expense line item:

1. OCR extracts merchant name, amount, currency, date (SPEND-148)
2. ML model predicts category with confidence score
3. If confidence > 85%: auto-apply category, show as pre-filled with "AI" badge
4. If confidence 60-85%: show top 3 suggestions, user picks one
5. If confidence < 60%: standard manual category picker
6. User overrides feed back into model training (SPEND-143)

## Success Metrics

- Reduce avg time-to-submit by 40%
- Reduce miscategorization rate from 23% to under 10%
- 70%+ of line items auto-categorized within 3 months of launch

## Dependencies

- SPEND-148: Receipt OCR accuracy must hit 90%+ (currently 74%, in review)
- ML model endpoint deployed to production (infra team, on track)
- Design review for confidence UI with Marina (scheduled March 26)

## Open Questions

- Should we show confidence scores to end users, or just use them internally? Leaning toward hiding them — users don't need to know the score, just whether it was auto-applied or suggested.
- How do we handle expenses that don't have a receipt (e.g., per diems, mileage)? Current thinking: use merchant + amount pattern matching as fallback.

## Risks

- OCR accuracy is the critical path. If SPEND-148 doesn't hit 90%, we either ship with lower confidence thresholds (more manual fallback) or delay.
- Model bias toward high-frequency categories (meals, transport) may mean long-tail categories (equipment, subscriptions) get poor predictions initially.
