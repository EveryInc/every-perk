# #ask-builders — Week of March 18–24, 2026

**Monday, March 18**

**Lauren Thomas** 10:40 AM
Can someone from eng confirm: is the group booking bundle price API returning the total for all travelers or per-person? Getting conflicting info in the docs.

**Tomas Berger** 10:55 AM
Total for all travelers. The per-person breakdown is in the `travelers[]` array. Docs are wrong — I'll update them.

**Lauren Thomas** 10:57 AM
Thanks Tomas. That explains the bug report from customer success.

---

**Wednesday, March 20**

**Morgane Lacousse** 2:10 PM
Has anyone seen issues with expense reports timing out for users with 50+ line items? Got two reports from enterprise customers this morning.

**Tomas Berger** 2:25 PM
Known issue. The PDF generation step is the bottleneck. Lydia's fix (SPEND-160) helped but we need to paginate the generation for large reports. Logged as a follow-up.

---

**Thursday, March 21**

**Ana Raquel Da Silva Costa** 9:00 AM
Question for the Spend team: is there a webhook or event I can subscribe to for "expense report submitted"? Trying to build automated tracking for our ops team.

**Tudor Tise** 9:15 AM
Not yet, but it's on my radar for Q2. Right now the best option is polling the API every 15 min. I know, not ideal. Will keep you posted when we have events.

**Ana Raquel Da Silva Costa** 9:17 AM
Polling it is. Thanks Tudor.

---

**Friday, March 22**

**Delia Di Filippantonio** 3:30 PM
Does anyone have a good way to pull expense data segmented by geo? I need EMEA vs Americas vs APAC for a research project. The dashboard only shows global.

**Agustina Di Clemente** 3:45 PM
I can pull that from the data warehouse. DM me the date range and categories you need and I'll get you a CSV by Monday.

**Delia Di Filippantonio** 3:47 PM
You're the best. Sending now.
