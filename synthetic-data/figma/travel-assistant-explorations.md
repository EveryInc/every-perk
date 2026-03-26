# Figma — AI Travel Assistant: Early Explorations

**Designer:** Marina Rybalko
**Status:** Exploration — NOT reviewed, NOT approved
**Last updated:** March 20, 2026

---

## Context

Tudor shared his feature brief for the AI Travel Assistant. I've started exploring what this could look like in the Perk app. These are rough explorations — not ready for eng handoff.

---

## Exploration 1: Floating Chat Bubble

Classic chat widget pattern — small circular button in the bottom-right corner of any screen. Tapping opens a chat overlay.

**Pros:**
- Familiar pattern (Intercom, Drift, etc.)
- Accessible from every screen
- Doesn't disrupt existing navigation

**Cons:**
- Feels like customer support, not a power user tool
- Overlaps with our existing help widget (would need to merge or replace)
- On mobile, the overlay takes up too much screen real estate

**My take:** Too generic. We should do something that feels more integrated.

---

## Exploration 2: Search Bar Upgrade

Replace the existing search bar at the top of the app with an AI-powered input. Users can type natural language queries directly into the same bar they use for searching trips and expenses.

**Pros:**
- Zero new UI — upgrades an existing element
- Natural mental model: "I search for things here"
- Progressive: basic search still works, AI queries get richer responses

**Cons:**
- Ambiguity: is the user searching or asking a question? "Tokyo flights" — search or query?
- Response format needs to fit in the search results area, which is limited
- Mobile search bar is small — might feel cramped for conversational input

**My take:** This is my preferred direction. The search bar is underutilized today. Making it smarter would feel like a natural evolution, not a bolt-on.

---

## Exploration 3: Dedicated Assistant Tab

New tab in the bottom navigation: "Assistant" (between "Trips" and "Expenses"). Full-screen chat interface.

**Pros:**
- Maximum space for rich responses (tables, charts, cards)
- Clear entry point — users know where to go
- Can show conversation history

**Cons:**
- Takes up a precious bottom nav slot (we only have 4 currently)
- Might feel disconnected from the context — if I'm looking at a trip, I have to switch tabs to ask about it
- Higher discoverability barrier — users have to learn this tab exists

**My take:** Too heavy for MVP. Maybe later if the assistant becomes a core workflow.

---

## Exploration 4: Contextual Assistant Panel

Slide-out panel from the right side (desktop) or bottom sheet (mobile). Triggered by a small "Ask" button that appears on relevant screens (trip detail, expense report, policy page).

**Pros:**
- Context-aware: the assistant knows what screen you're on
- Can reference the current trip/expense/policy in its responses
- Feels like a power-user tool, not a chatbot
- Doesn't take over the whole screen

**Cons:**
- More complex to implement — needs context passing from each screen
- Panel width is limited on desktop (400px?) which limits response formatting
- Multiple trigger points means testing every screen

**My take:** This is the most "Perk" feeling option. Context-aware assistance is the differentiator vs. a generic chatbot.

---

## Wireframe Notes — Exploration 2 (Search Bar Upgrade)

### Desktop
```
┌─────────────────────────────────────────────────────────────┐
│  🔍  Ask anything or search...                        [AI]  │
└─────────────────────────────────────────────────────────────┘
                          ↓ (on focus or AI query)
┌─────────────────────────────────────────────────────────────┐
│  🔍  Can I book business class to Tokyo?              [AI]  │
├─────────────────────────────────────────────────────────────┤
│                                                             │
│  ✈️  Business Class Policy                                  │
│                                                             │
│  Your role (Senior Consultant) qualifies for business       │
│  class on flights over 6 hours. Tokyo routes are            │
│  typically 11-12 hours, so you're eligible.                 │
│                                                             │
│  📋 Policy: EMEA-Travel-2026-v3, Rule 4.2                  │
│  👤 Approval: Auto-approved (flight duration > 6hrs)        │
│  💰 Budget remaining: €4,200 of €6,000 (Q2)               │
│                                                             │
│  [Search flights →]     [View full policy]                  │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

### Mobile
```
┌──────────────────────────┐
│  🔍  Ask or search...    │
├──────────────────────────┤
│                          │
│  ✈️  Business Class      │
│                          │
│  ✅ Eligible             │
│  Route: 11-12 hours      │
│  Policy: Rule 4.2        │
│  Budget: €4,200 left     │
│                          │
│  [Search] [View policy]  │
│                          │
└──────────────────────────┘
```

---

## Wireframe Notes — Exploration 4 (Contextual Panel)

### Desktop — Panel open on Trip Detail page
```
┌──────────────────────────────────┬──────────────────────────┐
│                                  │  AI Assistant             │
│  Trip: Berlin — Automotive       │                          │
│  Conference                      │  Based on your trip to   │
│                                  │  Berlin (Mar 30–Apr 2):  │
│  ✈️ BCN → BER  Mar 30 08:15     │                          │
│  🏨 Hotel Adlon  3 nights       │  Budget: €1,850 total    │
│  ✈️ BER → BCN  Apr 2 18:30      │  Hotel: €600 (3x €200)  │
│                                  │  Flights: €480           │
│  Status: Confirmed               │  Per diem: €270 (3x€90) │
│                                  │  Remaining: €500         │
│                                  │                          │
│                                  │  💡 Tip: The conference  │
│                                  │  venue has a negotiated  │
│                                  │  rate at Hotel Adlon.    │
│                                  │  Apply code AUTOCON26.   │
│                                  │                          │
│                                  │  ┌────────────────────┐  │
│                                  │  │ Ask about this trip │  │
│                                  │  └────────────────────┘  │
└──────────────────────────────────┴──────────────────────────┘
```

---

## Color & Typography Notes

- Assistant responses should use our existing type scale. Body in 14px/Geist, headings in 16px semi-bold.
- AI-generated content gets a subtle left border (2px, our brand teal at 40% opacity) to distinguish from static UI.
- The "[AI]" badge in the search bar matches the badge from expense categorization (SPEND-142 design). Reuse the same component.
- Response cards use our standard card component with 8px radius. No new patterns.

## Accessibility Considerations

- AI responses must be screen-reader compatible. Each response section has an aria-label.
- The search bar AI toggle must be keyboard-accessible (Tab → Enter to switch modes).
- Response content should not auto-scroll aggressively — user controls scroll position.
- Error states: if the AI can't answer, show a clear message with a "Search instead" fallback.

---

## Questions for Tudor

1. Do you want to prototype the search bar upgrade or the contextual panel first? I'd suggest search bar for speed.
2. Should the AI responses have a typing animation (streaming text) or appear all at once? I'd vote streaming — feels more alive.
3. Can we reuse the Slack bot's response formatting? Or does the in-app version need a different treatment?
