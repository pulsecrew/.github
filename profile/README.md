# Pulse

A unified AI health team — a suite of specialized AI agents that work together to provide holistic health, fitness, and nutrition guidance.

Instead of juggling five different apps for diet, fitness, sleep, and health tracking, Pulse combines them into one system where agents share context and surface cross-domain insights.

> **Example:** "You've been training heavy legs 3x this week but your protein intake is low and sleep dropped. Here's a high-protein meal from what's on sale at Kroger, and consider a rest day."

## Agents

| Agent | Role |
|-------|------|
| Orchestrator | Routes requests and aggregates responses across all agents |
| Chef / Dietician | Grocery deals, recipes, and meal planning |
| Personal Trainer | Workout plans and progress tracking |
| Health Advisor | Apple Health analysis and trend detection |
| Sleep Coach | Sleep quality and training/diet correlations |
| Accountability Partner | Check-ins, streaks, and motivation |

## Stack

Built on top of [OpenClaw AI](https://openclaw.ai) for agent infrastructure, gateway, and multi-channel messaging (WhatsApp, Telegram, Slack, Discord, etc.). The backend is FastAPI with a PostgreSQL + pgvector knowledge store, and a mobile app built with Expo.

Grocery deals are fetched by a standalone **flyers microservice** (TypeScript/Hono) that queries Flipp's backend API and uses Claude Haiku vision as a fallback for price extraction.

## Documentation

Full documentation is in the [`docs/`](../docs/README.md) folder, covering agents, infrastructure, and the roadmap.

For more information, visit the [Pulse Notion](https://www.notion.so/Pulse-313cb9b57d4081f6b731f7d34ab99042).
