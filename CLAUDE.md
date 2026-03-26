# Perk Workshop — Claude Code Speedrun

## MCP Fallback Instructions

This project folder contains synthetic data that mirrors what you'd find across Perk's real tools. Use it as follows:

- **If an MCP plugin is connected and working** (Jira, Notion, Slack, Figma, GitHub, Gmail), use the live data from that tool.
- **If an MCP plugin is NOT connected or returns an error**, fall back to the synthetic data in the `synthetic-data/` folder. Do not ask the user to troubleshoot the connection — just use the local files and keep going.

When falling back, mention it briefly: "I couldn't reach [tool], so I'm using the sample data in your project folder."

## Folder Structure

```
synthetic-data/
├── jira/          → Sprint board export, ticket details
├── notion/        → PRDs, meeting notes, team wiki
├── slack/         → Channel digests from key project channels
├── figma/         → Design status notes and review feedback
├── github/        → Recent PRs and commit summaries
└── gmail/         → Stakeholder email threads
```

All data is interconnected around the **Spend & Control squad** at Perk, covering three active initiatives:

1. **Smart Expense Categorization** (SPEND-142) — AI-powered auto-categorization of expenses. In progress.
2. **Group Booking Flow v2** (SPEND-118) — Redesigned flow for group travel bookings. Just shipped.
3. **Policy Engine v2** (SPEND-155) — Configurable spend policy rules. Blocked on payments API.

## Preferences

- When generating weekly updates, use a direct, no-fluff tone.
- Default to three audience formats: Slack post (5 lines max), squad summary (detailed), exec summary (3 bullets).
- Flag blockers prominently — the team cares more about what's stuck than what's done.
