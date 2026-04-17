# AgentTeamLand

> **The land where AI agent teams forge production software.**

## What is this?

AgentTeamLand is a framework for building production-grade software projects with teams of specialized AI agents. Every project follows the same architecture (Vertical Slice + Clean Architecture + Mediator on .NET 9), runs entirely in Docker, and is scaffolded by a single command.

## Quickstart

```bash
# Bootstrap on a fresh machine (installs /team + /save-learnings + /brainstorm + /rule + /create-new-project)
git clone https://github.com/agentteamland/team-manager.git \
  ~/.claude/repos/agentteamland/team-manager
~/.claude/repos/agentteamland/team-manager/install.sh

# In your project directory:
cd your-project/
/team install https://github.com/agentteamland/software-project-team.git
/create-new-project YourProjectName
```

The `/create-new-project` skill runs `/verify-system` automatically — you'll know the stack is healthy end-to-end before writing a single feature.

## Team Catalog

| Team | Description | Repo |
|---|---|---|
| **software-project-team** | 13 specialized agents for full-stack projects: .NET 9 API + Flutter + React + Postgres + RabbitMQ + Redis + Elasticsearch + MinIO | [/software-project-team](https://github.com/agentteamland/software-project-team) |

*More teams coming — contributions welcome.*

## Core Packages

| Package | What it does |
|---|---|
| [team-manager](https://github.com/agentteamland/team-manager) | `/team` skill + bootstrap `install.sh` |
| [core](https://github.com/agentteamland/core) | `/save-learnings`, `/verify-system`, `/wiki`, `/create-code-diagram` + global rules (memory-system, agent-structure, version-check) |
| [brainstorm](https://github.com/agentteamland/brainstorm) | `/brainstorm` skill — structured decision capture with document chain |
| [rule](https://github.com/agentteamland/rule) | `/rule` + `/rule-wizard` — capture coding/architecture rules |
| [create-project](https://github.com/agentteamland/create-project) | `/create-new-project` — 5-phase project scaffolder |

## Philosophy

- **API is the brain.** 99% of business logic lives in the API. Frontend and workers are thin bridges.
- **One architecture, every project.** Vertical Slice + Clean Architecture + martinothamar/Mediator. No alternatives.
- **Docker-only.** No local SDK installs. Flutter is the single exception (mobile toolchains don't run in Docker).
- **Agents have children.** `agent.md` holds identity; `children/` holds deep, topical knowledge.
- **Verify everything.** `/verify-system` proves the system works end-to-end — containers, ports, pipelines, auth, audit trail — before any deploy.

## License

MIT (each repo has its own LICENSE file).
