# User Interview — Meridian Systems

**Date:** March 14, 2026
**Interviewer:** Alex Walker
**Participant:** Daniel Fischer, Sales Director & Katrin Bauer, Travel Manager
**Company:** 1,800 travelers, mid-market plan, $180K ARR
**Recording:** Available in Dovetail (link redacted)

---

## Interview Transcript

**Alex:** Thanks for joining, both of you. I want to understand how your team handles travel booking and expenses, particularly for groups.

**Daniel:** Sure. I manage a 40-person sales team spread across EMEA. We do quarterly offsites, client dinners, conference travel — a lot of group bookings. Before Perk, this was all done through a travel agency. Expensive and slow.

**Alex:** How's the group booking experience been?

**Katrin:** Much better since the update last week, actually. I booked our Q2 offsite — 18 people going to Lisbon — using the new flow. The invite-and-collect-preferences approach is really intuitive. Before, I'd send a spreadsheet asking everyone for their preferences and then manually book one by one.

**Alex:** How long did the new flow take compared to the old approach?

**Katrin:** The new flow took maybe 20 minutes for 18 people. The old way? I'd spend half a day on spreadsheets and follow-up emails. Easily 4 hours.

**Daniel:** And that's Katrin's time — she's our Travel Manager. Her time is expensive.

**Alex:** Any issues with the new flow?

**Katrin:** One thing. Three of our sales directors wanted business class for the Lisbon flight, but everyone else was booking economy. The system couldn't handle that. It kept trying to bundle everyone into the same cabin class. I ended up booking the three directors separately.

**Alex:** Yeah, that's a known issue — SPEND-120. We're working on mixed cabin class support. Anything else?

**Katrin:** The preference step was a bit confusing for some travelers. A couple of people asked me "what am I supposed to do here?" The screen shows seat preference, meal preference, loyalty number, and special requests all at once. It's a lot of fields when all you want to do is confirm you're going on the trip.

**Daniel:** I'd say 5 out of 18 didn't complete the preference step at all. They just clicked the invite link, saw the form, and closed the tab. I had to ping them on Slack to complete it.

**Alex:** That's consistent with what we're seeing in the data — about 32% drop-off at the preference step. It might be too many fields upfront.

**Katrin:** Maybe just ask "Are you coming? Yes/No" first, and then let people optionally fill in preferences. Don't make the whole form feel mandatory.

**Alex:** That's a great idea. Let me note that down. [writing] Separate confirmation from preference collection.

**Daniel:** Can I switch topics? I want to talk about expenses.

**Alex:** Of course.

**Daniel:** My sales team submits a lot of receipts in multiple currencies. Euro, pounds, Swiss francs, Swedish krona — we operate in 8 countries. The receipt scanner gets the amount wrong probably 30% of the time for non-euro currencies.

**Alex:** 30%? That's higher than our overall average.

**Daniel:** For euro receipts it's fine — maybe 90% accurate. But put a Swiss franc receipt in front of it and it's a coin flip. The format is different — Switzerland uses an apostrophe as a thousands separator. So CHF 1'250.00 gets read as 1.250 or 250 depending on its mood.

**Katrin:** And Swedish receipts! The SEK amount is sometimes at the top, sometimes at the bottom, and the word "SUMMA" means total. The OCR doesn't seem to know that.

**Alex:** Really useful feedback. Our OCR team is actively working on multi-currency — this is exactly the kind of detail they need.

**Daniel:** I want to mention one more thing. We're coming up on our renewal review in April. My CFO saw a Navan demo and asked why we're not using that instead. I'm going to bat for Perk because I believe in the product, but I need to show progress on auto-categorization. That's the feature that will keep us on Perk.

**Alex:** I hear you. Nurdan — the PM for auto-categorization — would love to talk to you directly. Can we set up a call?

**Daniel:** Absolutely. Send me some times.

---

## Key Takeaways

1. **Group Booking v2 is a massive time save** — from ~4 hours to ~20 minutes for an 18-person trip. But mixed cabin class is a real pain point.
2. **Preference step UX needs simplification.** "Are you coming?" should be separate from detailed preferences. 5 of 18 travelers didn't complete the form.
3. **Multi-currency OCR is critical for EMEA customers.** Swiss franc (apostrophe separator) and Swedish krona ("SUMMA" keyword) are specific failure cases.
4. **Navan competitive pressure is real.** Meridian's CFO is evaluating alternatives. Auto-categorization is the retention lever.
5. **Renewal at risk** if auto-categorization doesn't ship before April 15 review.

## Quotes to Use

> "The old way? I'd spend half a day on spreadsheets and follow-up emails. Easily 4 hours."

> "Maybe just ask 'Are you coming? Yes/No' first, and then let people optionally fill in preferences."

> "Put a Swiss franc receipt in front of it and it's a coin flip."

## Follow-ups

- **Action:** Alex to connect Nurdan with Daniel for auto-categorization roadmap walkthrough.
- **Action:** Alex to share the CHF apostrophe separator and SEK "SUMMA" keyword issues with Tomas for SPEND-148.
- **Action:** Alex to add "separate confirmation from preferences" to SPEND-120 spec.
