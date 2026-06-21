<p align="center">
  <img src="https://raw.githubusercontent.com/agentteamland/workspace/main/assets/demo.gif" width="820" alt="atl demo"/>
</p>

<h1 align="center">AgentTeamLand</h1>

<p align="center">
  <b>The land where AI agent teams forge production software.</b><br/>
  <sub>A package manager for curated teams of AI agents — built for Claude Code.</sub>
</p>

---

## What is this?

AgentTeamLand is `atl`: a package manager for **teams of AI agents**. Each team bundles specialized agents (plus their skills and rules) for a kind of work — full-stack web apps, design systems, and more. Install a team once, and every agent it ships lands in your project's Claude Code directory, kept current and wired for background learning automatically.

Everything lives in one repo: **[agentteamland/atl](https://github.com/agentteamland/atl)** — the `atl` CLI, the core rules + skills, the first-party teams, and the docs.

## Install `atl`

| Platform | Command |
|---|---|
| **macOS / Linux** | `curl -fsSL https://raw.githubusercontent.com/agentteamland/atl/main/scripts/install.sh \| sh` |
| **Windows** | `irm https://raw.githubusercontent.com/agentteamland/atl/main/scripts/install.ps1 \| iex` |
| **Manual** | [Download from Releases](https://github.com/agentteamland/atl/releases) |

## Install a team

```bash
atl install software-project-team
```

Every agent / skill / rule the team provides lands in your project's `.claude/`. Browse the catalog with `atl search`.

## First-party teams

| Team | What it does |
|---|---|
| software-project-team | 13 agents for production full-stack software (.NET 9 + Flutter + React + Docker) |
| design-system-team | Native design-system + prototype generation, entirely inside Claude Code |

## Publish your own team

1. Put a `team.json` at your repo root — agents under `agents/<name>/`, skills under `skills/<name>/`, rules under `rules/<name>.md`.
2. Tag a release and add the `atl-team` GitHub topic.
3. Run `atl publish` — the index picks it up, so `atl search` + `atl install <handle>` make it available to everyone.

Full docs: **[agentteamland.github.io/docs](https://agentteamland.github.io/docs/)**.

## License

MIT — see the [atl](https://github.com/agentteamland/atl) repo.
