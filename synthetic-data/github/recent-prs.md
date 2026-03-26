# GitHub — Recent Pull Requests (perk/spend-service)

**Week of March 18–24, 2026**

---

## PR #1247 — Group Booking v2: production rollout to 100%
**Author:** @tomas-berger
**Status:** Merged (March 18)
**Reviewers:** @carlos-eng, @priya-eng
**Branch:** `feature/group-booking-v2-rollout`

**Description:**
Removes feature flag `group_booking_v2_enabled` and rolls out new group booking flow to all users. Includes cleanup of old flow code and legacy API endpoints.

**Files changed:** 23 files, +142 / -1,847 lines
- Removed `GroupBookingLegacyController` and associated tests
- Updated routing to point exclusively to v2 endpoints
- Cleaned up 6 unused database migrations
- Updated API docs

**CI:** All tests passing. No performance regression detected.

---

## PR #1251 — OCR: multi-currency extraction improvements
**Author:** @tomas-berger
**Status:** Open (March 22, updated March 24)
**Reviewers:** @priya-eng (approved), @carlos-eng (changes requested)
**Branch:** `feature/ocr-multi-currency`

**Description:**
Improves receipt OCR pipeline for multi-currency extraction. Adds preprocessing step for currency symbol detection before amount parsing. Targets SPEND-148.

**Key changes:**
- New `CurrencyDetector` module with support for 42 currency symbols
- Updated preprocessing pipeline: grayscale → denoise → currency detect → amount extract
- Added 200+ test receipts for EUR, GBP, CHF, SEK, NOK
- Accuracy improvement: 74% → 81% overall, 68% → 79% for multi-currency

**Review comment from @carlos-eng:**
"The CurrencyDetector is solid but we need to handle the edge case where € appears multiple times on a receipt (subtotal, tax, total). Currently it grabs the first occurrence. Should we take the largest amount as the total?"

**CI:** Tests passing. 3 flaky tests in receipt_parsing_test.py — pre-existing, not related to this PR.

---

## PR #1253 — Expense report PDF export: currency symbol fix
**Author:** @lydia-foster-eng
**Status:** Merged (March 21)
**Reviewers:** @tomas-berger (approved)
**Branch:** `fix/pdf-currency-symbols`

**Description:**
Fixes rendering of GBP (£) and EUR (€) symbols in PDF exports. Root cause: PDF generation library was defaulting to ASCII encoding. Switched to UTF-8 with embedded font subset. Also improved table alignment for multi-line descriptions.

**Files changed:** 4 files, +31 / -12 lines
**Resolves:** SPEND-160

---

## PR #1255 — Slack bot: weekly spend summary MVP
**Author:** @tudor-eng
**Status:** Open (March 23)
**Reviewers:** @tomas-berger (pending)
**Branch:** `feature/slack-spend-summary`

**Description:**
Adds a scheduled Slack bot that posts weekly spend summaries to configured channels. Posts every Monday at 9:00 AM in the channel's timezone.

**Summary includes:**
- Total spend (current week vs previous week)
- Top 5 categories by spend
- Top 3 largest individual expenses
- Number of policy violations flagged
- Trend arrow (↑/↓) for week-over-week

**Open question:** Pieter wants week-over-week comparison. Currently shows absolute numbers only. Will add percentage change in follow-up PR.

**Files changed:** 11 files, +487 / -0 lines

---

## PR #1256 — Mobile receipt capture: auto-crop
**Author:** @tomas-berger
**Status:** Open (March 24)
**Reviewers:** @carlos-eng (pending)
**Branch:** `feature/mobile-receipt-autocrop`

**Description:**
Adds auto-crop functionality to the mobile receipt capture camera. Uses edge detection to identify receipt boundaries and crops automatically. Perspective correction coming in next PR.

**Files changed:** 7 files, +234 / -18 lines
**Related:** SPEND-162
