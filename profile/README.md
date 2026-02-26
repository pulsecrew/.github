# Pulse

A unified AI health team — a suite of specialized AI agents that work together to provide holistic health, fitness, and nutrition guidance.

Instead of juggling five different apps for diet, fitness, sleep, and health tracking, Pulse combines them into one system where agents share context and surface cross-domain insights.

> **Example:** "You've been training heavy legs 3x this week but your protein intake is low and sleep dropped. Here's a high-protein meal from what's on sale at Kroger, and consider a rest day."

## Agents

All agents run inside [OpenClaw AI](https://openclaw.ai) as isolated multi-agent sessions. The Coach is the default contact — it handles triage and accountability, spawning specialists as needed.

| Agent | Role |
|-------|------|
| Coach | Default contact, triage/routing, check-ins, streaks, and motivation |
| Chef / Dietician | Grocery deals, recipes, and meal planning |
| Personal Trainer | Workout plans and progress tracking |
| Health Advisor | Apple Health analysis, trend detection, and sleep |

## Stack

Built on top of [OpenClaw AI](https://openclaw.ai) as the agent runtime — OpenClaw runs the agents, manages tool-calling loops, and handles multi-channel messaging (WhatsApp, Telegram, Slack, Discord, etc.). Agents call a TypeScript/Hono data API (Relay) for reads/writes to PostgreSQL + pgvector. Mobile app built with Expo.

Grocery deals are fetched by a standalone **flyers microservice** (TypeScript/Hono) that queries Flipp's backend API and uses Claude Haiku vision as a fallback for price extraction.

## Documentation

Full documentation is in the [`docs/`](../docs/README.md) folder, covering agents, infrastructure, and the roadmap.

For more information, visit the [Pulse Notion](https://www.notion.so/Pulse-313cb9b57d4081f6b731f7d34ab99042).
