---
name: research-html-discovery
description: Use when researching a repo, workflow, product idea, market, or technical topic, especially when the result should include sourced findings or a shareable HTML artifact.
metadata:
  commands: research, research-html, discovery
---

# Research HTML Discovery

Use this for research, discovery, and standalone HTML reports.

## Source Policy

- Default sources: local codebase, git history, and files the user provided.
- Web, Linear, Slack, Datadog, Mixpanel, Notion, and other MCP sources are opt-in unless the user asks for latest/current market or technical guidance.
- Never include real customer data in generated examples or HTML. Use synthetic data.
- Cite every non-trivial claim with file paths, URLs, issue IDs, PRs, or tool query context.
- Include a confidence level for recommendations and any extrapolation.

## Output Choice

- Use Markdown for short answers, commit messages, PR bodies, and anything under about 30 lines.
- Use a single-file HTML artifact when the result should be re-read, shared, compared, explored, or presented.
- If generating HTML, write one valid HTML5 file with inline CSS and JS under `./html-artifacts/<topic>-<YYYY-MM-DD>.html`.
- If `./design-system.html` or `./html-artifacts/design-system.html` exists, inspect it and reuse the visual language.

## Research Flow

1. Restate the question and sources used.
2. Gather evidence from the narrowest reliable sources first.
3. Separate confirmed facts from inference.
4. Highlight risks, gaps, contradictions, and stale information.
5. Finish with actionable next steps or a decision recommendation when requested.

## HTML Report Rules

- Put the main conclusion above the fold.
- Use tables for comparisons and timelines.
- Use inline SVG diagrams for architecture or workflow maps.
- Keep copy dense and scannable. Avoid marketing-style hero pages.
- Include a visible sources section with links or local file references.
