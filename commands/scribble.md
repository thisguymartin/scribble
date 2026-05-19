---
description: Create a standalone HTML artifact when Markdown would be too flat
argument-hint: "[topic, context, and preferred sources]"
---

Use the `scribble` skill and produce one self-contained HTML artifact.

The skill is the router: it picks the artifact type (`compare`, `walkthrough`, `tool`, `research`, `report`, `plan`, `deck`, `diagram`, `design`) from your prompt or asks one bucket question, then picks a theme (`editorial`, `utilitarian`, `minimal`) — `editorial` is the default when the artifact is a `report` / `research` / `plan` / `walkthrough` aimed at leadership / CTO / CEO / board. Override with `--theme <name>` or phrasing like "make it pretty" / "keep it plain".

Default to local codebase, git history, user-provided files, and read-only MCP sources. Web and external systems are opt-in: use them only if the user asks, provides a URL/source, asks for latest/current guidance, or after you state what online lookup is needed and get approval.

Write the artifact to `./html-artifacts/<topic>-<YYYY-MM-DD>.html`. Include visible sources, confidence, assumptions, risks, and the next action. For long-form types, include Problem breakdown → Approach → Alternatives before the body.

User request:

$ARGUMENTS
