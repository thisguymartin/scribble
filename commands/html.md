---
description: Create a standalone HTML artifact when Markdown would be too flat
argument-hint: "[topic, context, and preferred sources]"
---

Use the `html-effectiveness` skill and produce one self-contained HTML artifact.

Default to local codebase, git history, user-provided files, and read-only MCP sources. Web and external systems are opt-in: use them only if the user asks, provides a URL/source, asks for latest/current guidance, or after you state what online lookup is needed and get approval.

Write the artifact to `./html-artifacts/<topic>-<YYYY-MM-DD>.html`. Include visible sources, confidence, assumptions, risks, and the next action.

User request:

$ARGUMENTS
