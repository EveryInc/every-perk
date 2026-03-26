# #customer-voice — Week of March 18–24, 2026

**Monday, March 18**

**Julia Martinez** 11:30 AM
🎉 Quick shoutout — just got off a call with BrightPath Consulting. Their travel coordinator said the new group booking flow "saved her life" this morning. Booked a 12-person sales offsite in 15 minutes. Unsolicited praise, which is rare.

**Alex Walker** 11:35 AM
Amazing. Can we get a quote for the case study? Pieter has been asking for customer quotes for the QBR.

**Julia Martinez** 11:38 AM
Already asked. She's happy to go on record. Will send the exact quote to the marketing channel.

---

**Tuesday, March 19**

**Morgane Lacousse** 9:15 AM
Escalation from Apex Dynamics: their controller says approval rules "don't fire half the time." This is the third time they've reported this. Ticket ZD-8834. @neil can someone look?

**Neil Rogers** 9:30 AM
Looking now. This might be the race condition we found in Sprint 22 — thought it was fixed. Pulling up their account config.

**Neil Rogers** 10:45 AM
Found it. Their rules use "AND" conditions across two policy groups, and the evaluation engine short-circuits if the first group returns "no match." It's a logic bug, not a config issue. Filing SPEND-163.

**Morgane Lacousse** 10:50 AM
Thanks Neil. How urgent? They're threatening to escalate to their VP.

**Neil Rogers** 10:52 AM
I'll get Tomas to patch it this sprint. It's a targeted fix — won't affect other accounts.

---

**Wednesday, March 20**

**Julia Martinez** 2:00 PM
GlobalTech update — the timeout issue is getting worse. Susan P. (Finance Director) called me directly. Their quarterly close is March 31 and she has 12 reports stuck in the submission queue. She used the word "unacceptable" twice.

**Tomas Berger** 2:15 PM
I bumped the timeout for enterprise accounts as a hotfix but the real fix is pagination. Prioritizing for Sprint 25.

**Julia Martinez** 2:20 PM
Can we give her a personal update? She's very unhappy and they're a $380K ARR account.

**Pieter Odink** 2:30 PM
I'll call her directly. @julia can you set up a 15-min call for tomorrow?

---

**Thursday, March 21**

**Ana Raquel Da Silva Costa** 10:00 AM
Interesting feedback from Synthwave Digital (mid-market, 200 travelers): they love the product but their team lead said "Navan's mobile app is just faster." He specifically mentioned receipt upload speed. Is this something we're tracking?

**Tomas Berger** 10:15 AM
We know mobile receipt upload is slower than Navan — their camera module uses on-device ML for preprocessing, ours does it server-side. SPEND-162 (auto-crop) is step one. On-device preprocessing is on the H2 roadmap.

**Nurdan Fatoglu** 10:20 AM
Adding this to the competitive analysis doc. Third time I've heard the Navan mobile comparison this month.

---

**Friday, March 22**

**Delia Di Filippantonio** 4:00 PM
Ran the Q1 feedback analysis. Top 3 requested features across all feedback channels:
1. Auto-categorization (mentioned 89 times)
2. Better policy violation explanations (mentioned 54 times)
3. Faster mobile experience (mentioned 47 times)

Full report in Notion → Customer Feedback Tracker. @pieter @nurdan

**Pieter Odink** 4:15 PM
This aligns perfectly with our Q2 priorities. Good validation. Can you add this to the QBR deck as a slide?

**Delia Di Filippantonio** 4:17 PM
On it.

---

**Friday, March 22**

**Lauren Thomas** 5:10 PM
Late one — NordTech GmbH renewal call went well. They're happy with the PDF fix. Their CFO said "small things like this show you're listening." Renewing for 2 years.

**Pieter Odink** 5:15 PM
Great news. @lydia take a bow.

**Lydia Foster** 5:20 PM
🎉 Always nice when a 2-point ticket drives a 2-year renewal.
