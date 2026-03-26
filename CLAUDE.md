# Perk Workshop — Claude Code Speedrun

## MCP Fallback Instructions

This project folder contains synthetic data that mirrors what you'd find across Perk's real tools. Use it as follows:

- **If an MCP plugin is connected and working** (Jira, Notion, Slack, Figma, GitHub, Gmail), use the live data from that tool.
- **If an MCP plugin is NOT connected or returns an error**, fall back to the synthetic data in the `synthetic-data/` folder. Do not ask the user to troubleshoot the connection — just use the local files and keep going.

When falling back, mention it briefly: "I couldn't reach [tool], so I'm using the sample data in your project folder."

## Folder Structure

```
synthetic-data/
├── jira/
│   ├── sprint-board.csv               → Current sprint with all active tickets
│   ├── support-tickets-march.csv      → Customer support ticket export (23 tickets)
│   └── weekly-metrics-q1-2026.csv     → 12 weeks of product metrics (raw data)
│
├── notion/
│   ├── squad-wiki.md                  → Team roster, Q2 priorities, rituals
│   ├── prd-smart-expense-categorization.md  → Active PRD for SPEND-142
│   ├── prd-draft-expense-ai-v2-DO-NOT-SHARE.md → ⚠️ Incomplete draft PRD for v2
│   ├── meeting-notes-spend-control-mar21.md    → Weekly sync notes
│   ├── meeting-notes-design-review-mar19.md    → Design review (confidence UI)
│   ├── meeting-notes-leadership-sync-mar17.md  → Leadership sync (cross-org)
│   ├── meeting-notes-retro-sprint23.md         → Sprint 23 retrospective
│   ├── product-strategy-draft-h2-2026.md       → H2 strategy with deliberate gaps
│   ├── roadmap-q2-q3-2026.md          → Approved roadmap (dates conflict with PRD)
│   ├── competitor-landscape-2026.md    → Competitive analysis (partial)
│   ├── feature-brief-travel-assistant.md → AI Travel Assistant exploration
│   ├── customer-feedback-tracker.md    → NPS, CSAT, advisory board notes
│   ├── metrics-definitions-spend-control.md → Metric definitions + discrepancies
│   ├── dashboard-requirements-pieter.md     → Dashboard requirements from Pieter
│   ├── buyer-personas-2026.md          → 5 buyer personas with objections
│   ├── landing-page-copy-expense-ai.md → Draft landing page copy (has issues)
│   ├── user-interview-globaltech-mar12.md   → Full transcript — Finance Director
│   ├── user-interview-meridian-mar14.md     → Full transcript — Sales Dir + Travel Mgr
│   └── user-interview-brightpath-mar18.md   → Full transcript — Controller
│
├── slack/
│   ├── spend-control-digest.md        → #spend-control team channel
│   ├── ask-builders-digest.md         → #ask-builders cross-team questions
│   ├── customer-voice-digest.md       → #customer-voice escalations & praise
│   ├── competitor-intel-digest.md     → #competitor-intel market moves
│   └── travel-assistant-brainstorm.md → Brainstorm thread on AI assistant
│
├── figma/
│   ├── design-status.md               → Current design status for all initiatives
│   └── travel-assistant-explorations.md → 4 UI explorations with wireframes
│
├── github/
│   └── recent-prs.md                  → 5 recent PRs with review comments
│
└── gmail/
    ├── stakeholder-threads.md         → VP email, escalations, QBR data request
    ├── customer-escalations-q1.md     → Customer emails (GlobalTech, Meridian, BrightPath, Apex)
    ├── competitive-analysis-request.md → VP requesting competitive analysis for board
    └── landing-page-feedback.md       → Landing page review thread with disagreements
```

All data is interconnected around the **Spend & Control squad** at Perk, covering three active initiatives:

1. **Smart Expense Categorization** (SPEND-142) — AI-powered auto-categorization of expenses. In progress.
2. **Group Booking Flow v2** (SPEND-118) — Redesigned flow for group travel bookings. Just shipped.
3. **Policy Engine v2** (SPEND-155) — Configurable spend policy rules. Blocked on payments API.

### Intentional Chaos (for exercises)

The data contains deliberate inconsistencies to make exercises realistic:
- **Conflicting dates:** The roadmap says AI Categorization ships April 8; the PRD says April 15
- **Metric discrepancies:** Amplitude shows 68% group booking conversion; backend shows 64%
- **Outdated claims:** Landing page says "85%+ accuracy" but the model is at 82%
- **Unfinished work:** The v2 PRD is marked "DO NOT SHARE" and has incomplete sections
- **Overdue action items:** Sprint 22 retro had 2 actions carried forward undone
- **Team count mismatch:** Strategy doc says 10 people but lists more names
- **Orphaned research:** The competitor landscape doc hasn't been updated for the board request
- **Stale info:** Landing page claims SOC 2 Type II and data sovereignty that aren't real yet

## Preferences

- When generating weekly updates, use a direct, no-fluff tone.
- Default to three audience formats: Slack post (5 lines max), squad summary (detailed), exec summary (3 bullets).
- Flag blockers prominently — the team cares more about what's stuck than what's done.
