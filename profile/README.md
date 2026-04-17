<p align="center">
  <img src="https://raw.githubusercontent.com/agentteamland/workspace/main/assets/demo.gif" width="820" alt="atl demo"/>
</p>

<h1 align="center">AgentTeamLand</h1>

<p align="center">
  <b>The land where AI agent teams forge production software.</b><br/>
  <sub>A package ecosystem for curated teams of AI agents.</sub>
</p>

---

## What is this?

AgentTeamLand is a package manager + registry for **teams of AI agents**. Each team bundles a set of specialized agents (plus their skills and rules) for a specific kind of work — full-stack web apps, data pipelines, mobile-first products, game servers, whatever you need.

Install a team once, and every agent it contains is symlinked into your project's Claude Code directory. Teams can extend other teams, override agents by name, and exclude ones you don't need — so building on someone else's work doesn't mean maintaining a fork.

## Install `atl`

| Platform | Command |
|---|---|
| **macOS / Linux** | `brew install agentteamland/tap/atl` |
| **Windows (Scoop)** | `scoop bucket add agentteamland https://github.com/agentteamland/scoop-bucket`<br/>`scoop install atl` |
| **Windows (winget)** | `winget install agentteamland.atl` *(awaiting Microsoft review)* |
| **Manual** | [Download from Releases](https://github.com/agentteamland/cli/releases) |

## Install a team

```bash
atl install software-project-team
```

That's it. The team clones into a shared cache, and every agent / skill / rule it provides symlinks into your project's `.claude/`. You can now start using `/create-new-project`, `/verify-system`, or invoke any of the 13 specialized agents from Claude Code.

## Team catalog

Teams are listed in the public [**registry**](https://github.com/agentteamland/registry). Install any of them by short name.

| Team | Status | Stack | Install |
|---|---|---|---|
| [software-project-team](https://github.com/agentteamland/software-project-team) | ✅ verified | .NET 9 + Flutter + React + Docker | `atl install software-project-team` |
| [starter-extended](https://github.com/agentteamland/starter-extended) | example | *extends software-project-team* | `atl install starter-extended` |

*More teams incoming. [Submit yours](https://github.com/agentteamland/registry/blob/main/CONTRIBUTING.md).*

## Core packages

If you're building tooling on top of AgentTeamLand, these are the pieces you work with:

| Package | What it does |
|---|---|
| [cli](https://github.com/agentteamland/cli) | `atl` binary — the package manager CLI (Go) |
| [registry](https://github.com/agentteamland/registry) | Public `teams.json` — the catalog you see above |
| [team-manager](https://github.com/agentteamland/team-manager) | `/team` skill + bootstrap `install.sh` (inside Claude Code) |
| [core](https://github.com/agentteamland/core) | `/save-learnings`, `/wiki`, `/create-code-diagram`, global rules, JSON schemas |
| [brainstorm](https://github.com/agentteamland/brainstorm) | `/brainstorm` skill for structured decision capture |
| [rule](https://github.com/agentteamland/rule) | `/rule` + `/rule-wizard` |

## Philosophy

- **API is the brain.** 99% of business logic lives in the API. Frontend and workers are thin bridges.
- **One architecture, every project.** Vertical Slice + Clean Architecture + martinothamar/Mediator. No alternatives.
- **Docker-only.** No local SDK installs. Flutter is the single exception.
- **Agents have children.** `agent.md` holds identity; `children/` holds deep, topical knowledge.
- **Verify everything.** `/verify-system` proves the system works end-to-end — containers, ports, pipelines, auth — before any deploy.

## Author your own team

If your work needs a different stack, build a team:

1. Create a git repo with a `team.json` at its root (validates against the [team schema](https://github.com/agentteamland/core/blob/main/schemas/team.schema.json))
2. Add agents under `agents/<name>/agent.md`, skills under `skills/<name>/skill.md`, rules under `rules/<name>.md`
3. (optional) Extend an existing team with `extends: "software-project-team@^1.0.0"`, override agents by name, exclude ones you don't want
4. Open a PR against [agentteamland/registry](https://github.com/agentteamland/registry) — CI validates schema + URL reachability, maintainers review, your team goes live

Full guide: [scaffolder-spec.md](https://github.com/agentteamland/core/blob/main/docs/scaffolder-spec.md).

## License

MIT — each repo in the org has its own LICENSE file.
