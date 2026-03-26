# User Interview — GlobalTech Inc

**Date:** March 12, 2026
**Interviewer:** Nurdan Fatoglu
**Participant:** Susan Park, Finance Director, GlobalTech Inc
**Company:** 2,400 travelers, enterprise plan, $380K ARR
**Recording:** Available in Dovetail (link redacted)

---

## Interview Transcript

**Nurdan:** Thanks for taking the time, Susan. I want to understand how your team handles expense management day-to-day, and where the biggest pain points are.

**Susan:** Happy to help. Honestly, the biggest pain point is simple: volume. We have 2,400 travelers submitting expenses constantly. My team of 6 reviews and reconciles everything. It's relentless.

**Nurdan:** Walk me through a typical week for your team.

**Susan:** Sure. Monday is the worst day because people submit over the weekend after business trips. We'll get 200-300 expense reports on Monday alone. Each report has anywhere from 5 to 80 line items. My team reviews each one for policy compliance, correct categorization, and supporting documentation.

**Nurdan:** How long does a typical review take?

**Susan:** For a clean report — maybe 3 minutes. But "clean" is the exception. About 25% of reports have at least one miscategorized expense. And when that happens, we have to send it back to the employee for correction, which adds 2-3 days to the cycle. Our average time from submission to approval is 4.5 days, and our target is 2 days.

**Nurdan:** What kinds of miscategorization do you see most often?

**Susan:** The classics. People put meals under "entertainment." Conference fees under "training." Uber rides under "parking" for some reason — maybe because the icon looks similar? And international expenses are a mess because people don't always convert currencies correctly, or the receipt is in a language they don't read so they guess the category.

**Nurdan:** If we could auto-categorize expenses with, say, 80-85% accuracy, how would that change your team's workflow?

**Susan:** That would be transformative. Even 80% would mean we're only manually reviewing 1 in 5 items instead of every single one. My team could shift from data entry to exception handling, which is what they should be doing anyway.

But I need to be honest — accuracy matters more than speed. If the auto-categorization is wrong 20% of the time and we trust it, we end up with a bigger mess than manual categorization. We'd need a way to audit which categories were AI-assigned and review those on a sampling basis.

**Nurdan:** That's really helpful. What confidence level would make you comfortable with full auto-categorization?

**Susan:** I'd want 95%+ for auto-apply — meaning the system fills it in and the user doesn't even think about it. For anything below that, show the user some options and make them choose. Don't auto-apply if you're not very confident. A wrong auto-applied category is worse than asking the user to pick.

**Nurdan:** Makes sense. Let me ask about a different topic — the expense report submission experience for your travelers. What do they complain about most?

**Susan:** Time. They all say it takes too long. The category picker is the #1 complaint. We have 47 expense categories — it's a long list. People scroll and scroll. On mobile it's even worse.

Second complaint: receipts. Taking a photo, waiting for it to upload, then the OCR reads the wrong amount half the time. People end up typing everything manually anyway, which defeats the purpose.

Third: they don't understand policy violations. Someone gets a red flag on an expense and the message just says "Policy violation." No detail on which policy, what the threshold is, or what they should do differently. They end up pinging my team on Slack asking "what did I do wrong?"

**Nurdan:** That third one is interesting. Would better violation messages reduce the back-and-forth?

**Susan:** Absolutely. If the message said "This expense exceeds the $150/night hotel policy for your region. Your manager needs to approve expenses above this threshold" — that's actionable. The employee either knows they need to justify it or knows they need to find a cheaper option next time.

**Nurdan:** Last question: if you could wave a magic wand and fix one thing about Perk, what would it be?

**Susan:** Auto-categorization. No contest. If you can make my 47-category picker disappear for 80%+ of expenses, you'll save my travelers thousands of hours per year and my team can focus on actual finance work instead of data entry.

Second on the list: fix the timeout issue for large reports. But I know you're working on that. [laughs]

**Nurdan:** [laughs] We are indeed. Thank you Susan, this is incredibly helpful.

---

## Key Takeaways

1. **Volume is the core problem.** 200-300 reports per Monday, team of 6 reviewing manually. Auto-categorization would fundamentally change their workflow.
2. **Accuracy over speed.** Susan wants 95%+ for auto-apply. Below that, suggest but don't auto-fill. Wrong auto-applied categories are worse than manual.
3. **47 expense categories** — the picker is the biggest UX complaint from travelers.
4. **Policy violation messages are useless** without specificity. Generic "Policy violation" creates unnecessary support load.
5. **OCR trust is low.** Even when OCR extracts data, users manually verify because they've been burned before.
6. **4.5 day average submission-to-approval** vs. 2-day target. Miscategorization is the primary cause of delays.

## Quotes to Use

> "If you can make my 47-category picker disappear for 80% of expenses, you'll save my travelers thousands of hours per year."

> "A wrong auto-applied category is worse than asking the user to pick."

> "The message just says 'Policy violation.' No detail on which policy, what the threshold is, or what they should do differently."
