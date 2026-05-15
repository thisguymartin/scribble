# Scribble

Personal research and discovery skills for agent workflows. Quick HTML sketches to debug, explore, and surface patterns.

This repo is skills-first. The main install path is the Vercel `skills` CLI because it can install the same `skills/` directory into Codex, Claude Code, Cursor, Gemini CLI, OpenCode, and other agents.

## Install

From `/Users/thisguymartin/personal-workspace`:

```bash
npx skills add ./scribble --list
npx skills add ./scribble --all -g
```

Install into only the current project instead of globally:

```bash
npx skills add ./scribble --all
```

Install globally for Codex only:

```bash
npx skills add ./scribble -a codex -g
```

After publishing the repo publicly:

```bash
npx skills add mpatino117/scribble --all -g
```

To avoid CLI telemetry while installing:

```bash
DISABLE_TELEMETRY=1 npx skills add ./scribble --all -g
```

## Skills

- `html-effectiveness` - broad single-file HTML artifacts when Markdown is too flat.
- `research-html-discovery` - research reports and HTML discovery artifacts.
- `tool-evaluation` - maintenance, license, adoption, cost, and stack-fit reviews.
- `source-synthesis` - compact sourced summaries that separate facts from inference.

## Flow

How a user request routes through the skills and where the optional [caveman](https://github.com/JuliusBrussee/caveman) skill kicks in:

```mermaid
flowchart TD
    U([User request]) --> R{What kind of work?}

    R -->|Shareable or visual output,<br/>plan, PR review, explainer,<br/>prototype, report, editor| HE[html-effectiveness]
    R -->|Research repo, market,<br/>UI plan, technical topic| RHD[research-html-discovery]
    R -->|Combine sources into a memo<br/>or planning handoff| SS[source-synthesis]
    R -->|Pick between libraries,<br/>APIs, SaaS, MCPs| TE[tool-evaluation]

    HE --> SRC{Sources}
    SRC -->|Local repo, git,<br/>provided files, read-only MCP| AP[artifact-patterns.md<br/>source ledger labels,<br/>visual models,<br/>Before Emitting checklist,<br/>agent handoff format]
    SRC -. web only if requested<br/>or explicitly approved .-> AP
    RHD --> AP[artifact-patterns.md<br/>source ledger labels,<br/>visual models,<br/>Before Emitting checklist,<br/>agent handoff format]
    SS --> AP
    TE --> AP

    AP --> OUT{Output shape}
    OUT -->|HTML artifact| HTML[HTML body copy]
    OUT -->|Next-agent / handoff prompt| HAND[Handoff bullets]

    HTML -.if installed.-> CMLITE[caveman <b>lite</b><br/>plain English,<br/>no marketing voice]
    HAND -.if installed.-> CMFULL[caveman <b>full</b><br/>fragments OK,<br/>drop articles,<br/>imperatives only]

    CMLITE --> DELIVER([Deliver to user])
    CMFULL --> DELIVER
    HTML --> DELIVER
    HAND --> DELIVER

    classDef skill fill:#1f6feb,stroke:#0b3d91,color:#fff;
    classDef shared fill:#8957e5,stroke:#4c2889,color:#fff;
    classDef caveman fill:#f0883e,stroke:#9e5217,color:#fff;
    class HE,RHD,SS,TE skill;
    class AP shared;
    class CMLITE,CMFULL caveman;
```

Read it as: `html-effectiveness` is the broad "make this readable as HTML" path. The other skills stay narrower helpers for research, synthesis, and tool evaluation. Local sources are the default; web lookup only happens when requested or explicitly approved. Output is either an HTML artifact for humans or a handoff prompt for an agent. If caveman is installed globally, those outputs route through `lite` or `full` mode for token savings and plain-English copy.

## Recommended Companion Skill — caveman

The skills above reference the official [caveman](https://github.com/JuliusBrussee/caveman) skill for two things:

- **Inter-agent handoffs** (`full` mode) — terse, fragment-OK prompts for the next agent. Cuts ~75% of inter-agent tokens.
- **HTML artifact body copy** (`lite` mode) — plain English, no marketing voice, full sentences kept so humans read it cleanly.

Install once globally so the references resolve:

```bash
npx skills add JuliusBrussee/caveman -g
```

The full upstream suite also ships `caveman-commit`, `caveman-review`, `caveman-compress`, `caveman-stats`, `cavecrew`, and a `SessionStart` hook for always-on activation in Claude Code. See upstream for install paths per agent.

## Optional Plugin Installs

The repo also includes plugin metadata for Codex and Claude Code.

Codex local marketplace:

```bash
codex plugin marketplace add /Users/thisguymartin/personal-workspace/scribble
```

Then open `/plugins`, choose `Scribble`, and install it.

Claude Code local marketplace:

```text
/plugin marketplace add /Users/thisguymartin/personal-workspace/scribble
/plugin install scribble@scribble
```

## References

- Vercel skills CLI: https://github.com/vercel-labs/skills
- Agent Skills spec: https://agentskills.io/specification
- Codex plugins: https://developers.openai.com/codex/plugins
- Claude Code plugins: https://code.claude.com/docs/en/plugins
