# Feature Brief: AI Travel Assistant

**Author:** Tudor Tise
**Status:** Draft — Exploring
**Created:** March 15, 2026
**Last updated:** March 20, 2026

---

## The Idea

An AI-powered travel assistant that lives inside Perk's chat interface (and Slack via the bot). Travelers can ask natural-language questions about their trips, policies, and expenses instead of navigating through menus.

## Example Interactions

**Trip Planning:**
> "I need to fly to Berlin March 30–April 2 for the automotive conference. What's my budget?"
> → Assistant checks the user's role, applicable travel policy, and conference-specific overrides. Returns: "Your policy allows up to €200/night for hotels and economy flights. For the Automotive Leaders Conference, your manager has approved a €300/night override. Want me to search for flights and hotels?"

**Expense Questions:**
> "How much have I spent on client dinners this quarter?"
> → Queries expense data, returns total with breakdown by client.

**Policy Lookups:**
> "Can I book business class to Tokyo?"
> → Checks role, route length (>6 hours), and policy rules. Returns: "Economy is standard for your role, but business class is available for flights over 6 hours with manager approval. Want me to send an approval request?"

**Receipt Help:**
> "I have a receipt in Japanese — can you help me categorize it?"
> → Uses OCR + translation to extract merchant, amount, and suggest category.

## Why Now

1. **AI categorization is shipping** (SPEND-142). The ML infrastructure for understanding expenses is being built. The assistant is a natural extension.
2. **Slack bot is live** (SPEND-161). Tudor already has the Slack integration framework. Adding conversational AI is incremental.
3. **Policy Engine v2** (SPEND-155) will have structured rules that the assistant can query programmatically.
4. **Competitive pressure.** Navan launched "Ava" (their AI assistant) in January. Three customers have mentioned it in feedback calls.

## User Personas

**The Frequent Traveler (e.g., Daniel Fischer, Meridian Systems)**
- Travels 2-3x per month across multiple countries
- Wants quick answers without navigating through settings
- Submits 20+ expenses per trip
- Currently wastes 30 min/trip looking up policies and categorizing

**The Travel Manager (e.g., Katrin Bauer, Meridian Systems)**
- Manages travel for 40+ people
- Needs visibility into team spending without running reports
- Often asked "what's our policy on X?" by travelers
- Currently answers the same questions over and over

**The Finance Admin (e.g., Susan Park, GlobalTech Inc)**
- Reviews and reconciles hundreds of expense reports
- Needs to quickly check status of specific reports or travelers
- Currently relies on CSV exports and manual searches

## Scope — MVP

For the MVP, focus on:
1. **Policy Q&A** — "Can I book X?" / "What's my budget for Y?"
2. **Expense queries** — "How much did I spend on Z?" / "What's my pending total?"
3. **Trip status** — "When is my flight?" / "Is my hotel confirmed?"

NOT in MVP:
- Booking actions (searching/booking flights or hotels through the assistant)
- Approval workflows through chat
- Receipt scanning through chat
- Multi-turn complex interactions

## Technical Approach (Initial Thinking)

- Use existing Slack bot infrastructure (SPEND-161) as the interface layer
- AI SDK for the LLM integration — stream responses for natural feel
- Tool calling for structured data access: query_policy, query_expenses, query_trips
- Start with Anthropic's Claude for the model — good at structured tool calling
- Consider Vercel AI Gateway for provider flexibility later

## Open Questions

1. **Slack-first or app-first?** Tudor thinks Slack is the right starting point — people are already there. But Pieter wants it in the app too. Need to decide where to invest first.
2. **How do we handle hallucination?** The assistant must not make up policy rules. Need guardrails: if the policy lookup returns no match, say "I don't have a policy for this — please check with your manager" instead of guessing.
3. **Privacy scope.** Should a manager be able to ask the assistant about their direct report's expenses? What's the authorization model?
4. **Cost model.** Each query will cost ~$0.01-0.05 in LLM API calls. At 1,000 queries/day across all customers, that's $30-50/day. Acceptable? Need to check with finance.
5. **What happens when the assistant is wrong?** We need a feedback mechanism — thumbs up/down on responses, with low-rated responses flagged for review.

## Competitors

- **Navan Ava** — launched January 2026, conversational booking + expense queries. Mixed reviews: good for simple questions, struggles with complex multi-leg trips.
- **SAP Concur "ConcurBot"** — Slack bot for expense status. Very limited — basically just "where is my expense report?"
- **Brex AI** — expense categorization + policy checking, not conversational.

## Next Steps

- [ ] Get Pieter's feedback on this brief
- [ ] Align with Nurdan on AI infrastructure overlap with SPEND-142
- [ ] Sketch 3-4 key interaction flows with Marina
- [ ] Cost estimate from eng (Tomas)
- [ ] Customer validation: would GlobalTech, Meridian, BrightPath use this?
