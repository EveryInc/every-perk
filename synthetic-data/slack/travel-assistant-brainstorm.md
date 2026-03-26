# #spend-control — AI Travel Assistant Brainstorm Thread

**March 20, 2026**

---

**Tudor Tise** 11:00 AM
Hey team — I've been noodling on an idea and wrote up a brief. What if we built an AI travel assistant that lets travelers ask questions in natural language? "Can I book business class to Tokyo?" / "How much have I spent on dinners this month?" / "What's my remaining budget?"

I think we can build on the Slack bot infrastructure (SPEND-161) and the ML work Nurdan's doing for auto-categorization. Shared the full brief in Notion → Feature Brief: AI Travel Assistant.

Thoughts? Is this too ambitious for Q2, or should we push for it?

---

**Nurdan Fatoglu** 11:15 AM
Love this. The ML model we're building for SPEND-142 can serve double duty — it already understands expense categories, merchants, and amounts. Adding a query interface on top would be incremental.

One concern: the policy lookup piece. If the assistant says "you're allowed to book X" and it's wrong, that's a trust-destroying moment. We'd need to make sure the policy engine (SPEND-155) returns structured rules, not just yes/no. The assistant needs to cite the specific policy.

---

**Marina Rybalko** 11:22 AM
I've already started sketching some explorations. Four directions — floating chat, search bar upgrade, dedicated tab, and contextual panel. I think the search bar upgrade is the right starting point. It's the least disruptive and the most "Perk."

Will share the explorations in Figma later today.

---

**Alex Walker** 11:30 AM
Big fan. The #1 question I hear from travel managers: "What's our policy on X?" They're looking it up in a PDF or asking their admin. If we can answer that in 2 seconds via chat, that's a clear win.

Question: should this be traveler-facing first or admin-facing? Travel managers and finance teams have very different queries.

---

**Tudor Tise** 11:35 AM
Good question. My instinct: traveler-facing first (simpler queries, higher volume, easier to test), admin-facing in v2 (more complex but higher-value per query).

---

**Neil Rogers** 11:40 AM
I'm cautiously optimistic. A few concerns:

1. **Policy accuracy is non-negotiable.** If the assistant says "you can book this" and the policy engine disagrees, we have a compliance problem. The assistant MUST be grounded in the actual policy engine, not LLM knowledge.

2. **Authorization model.** A manager asking "how much has my team spent?" is fine. A random employee asking the same about a different team is not. We need to think about data access.

3. **Timing.** We're already stretched with SPEND-142, SPEND-148, and SPEND-155. Do we have the bandwidth to start a 4th initiative?

---

**Pieter Odink** 11:55 AM
Great thread. I want to be careful about scope creep here. We have 3 top-priority initiatives and they're all either in progress or blocked.

BUT — Navan launched Ava in January and three customers have mentioned it. This is strategic. I don't want us playing catch-up.

Proposal: **Tudor writes a more detailed spec by April 1. We evaluate at Q2 planning. If Policy Engine v2 ships on time, we have room for this in Q2. If not, it's Q3.**

Don't start building yet. But keep exploring. Marina's design explorations and Tudor's spec are good uses of time.

---

**Tudor Tise** 12:00 PM
Works for me. I'll have a full spec by April 1. @marina want to jam on the search bar direction this week?

**Marina Rybalko** 12:02 PM
Tomorrow 2pm?

**Tudor Tise** 12:03 PM
Done.

---

**Tomas Berger** 12:15 PM
Quick eng perspective: the Slack bot framework (SPEND-161) is modular enough to support this. The webhook handler, response formatter, and scheduling pieces are all separate. Adding an AI query handler would be a new module, not a rewrite.

For the in-app version, we'd need a new API endpoint and a streaming response setup. Doable but not trivial — maybe 2-3 sprint's worth of eng work for MVP.

Cost estimate: if we use Claude (sonnet tier), each query is roughly $0.003-0.01 depending on context size. At 1K queries/day, that's $3-10/day, or ~$200/month. Way within budget.

---

**Nurdan Fatoglu** 12:25 PM
@tomas that cost estimate is helpful. One optimization: we could cache common policy questions. "Can I book business class?" doesn't need a fresh LLM call every time — the policy rules don't change hourly. Cache the structured policy response and only call the LLM for novel queries.

---

**Mauro Spadaro** 12:30 PM
If we build this, I want to make sure the notification system integrates. Imagine: you book a trip, the assistant automatically tells you what documents you need, what expenses to expect, and what your budget is. Push notification on the morning of your trip: "Your flight to Berlin is at 8:15. Don't forget your passport. Based on your 3-night stay, your estimated total is €1,850."

---

**Tudor Tise** 12:35 PM
Mauro that's the dream state. Let's crawl first — answer questions reliably. Then walk — proactive notifications. Then run — full trip management through chat.

---

**Pieter Odink** 12:45 PM
Good discussion. To summarize:
- Tudor: full spec by April 1 ✅
- Marina: continue design explorations ✅
- Nurdan: flag any AI infra overlap with SPEND-142 ✅
- Tomas: rough eng effort estimate in the spec ✅
- Neil: document the policy accuracy and authorization requirements ✅

Nobody starts building until we evaluate at Q2 planning. Clear?

Everyone: 👍
