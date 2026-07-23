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

AgentTeamLand is `atl`: a package manager for **teams of AI agents**. Each team bundles specialized agents (plus their skills and rules) for a kind of work — autonomous software delivery, a personal advisor, a shared profile, and more. Install a team once, and every agent it ships lands in your project's Claude Code directory, kept current and wired for background learning automatically.

Everything lives in one repo: **[agentteamland/atl](https://github.com/agentteamland/atl)** — the `atl` CLI, the core rules + skills, and the docs.

## Install `atl`

| Platform | Command |
|---|---|
| **macOS / Linux** | `curl -fsSL https://raw.githubusercontent.com/agentteamland/atl/main/scripts/install.sh \| sh` |
| **Windows** | `irm https://raw.githubusercontent.com/agentteamland/atl/main/scripts/install.ps1 \| iex` |
| **Manual** | [Download from Releases](https://github.com/agentteamland/atl/releases) |

## Install a team

```bash
atl search                      # browse the catalog
atl install <handle>/<team>
```

Every agent / skill / rule the team provides lands in your project's `.claude/`.

## First-party teams

The v1-era teams were retired in July 2026 and **rebuilt on the v2 platform**. Three ship today — install any with `atl install agentteamland/<team>`:

| Team | What it does |
|---|---|
| **profile-team** | A shared, cross-project profile of the people, places, and things in your world — the memory layer the other teams build on. |
| **personal-advisory-team** | An honest, wise advisor that comes to know you across conversations and, because it won't flatter you, becomes the one you run to. |
| **delivery-team** | An autonomous software-delivery org — analysts, PM, tech-lead, testers, developers — that runs a real sprint/Scrum loop on Azure DevOps or GitHub. |

More are on the way — watch the [atl repo](https://github.com/agentteamland/atl) for releases.

## Publish your own team

1. Put a `team.json` at your repo root — agents under `agents/<name>/`, skills under `skills/<name>/`, rules under `rules/<name>.md`.
2. Tag a release and add the `atl-team` GitHub topic.
3. Run `atl publish` — the index picks it up, so `atl search` + `atl install <handle>` make it available to everyone.

Full docs: **[docs.agentteamland.com](https://docs.agentteamland.com/)**.

## License

MIT — see the [atl](https://github.com/agentteamland/atl) repo.
