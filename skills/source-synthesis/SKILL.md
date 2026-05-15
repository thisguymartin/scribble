---
name: source-synthesis
description: Use when combining documents, links, issues, PRs, logs, artifacts, MCP context, or research sources into a sourced summary, decision memo, or planning handoff.
---

# Source Synthesis

Use this when the user provides or requests multiple sources and wants the useful truth, not a pile of excerpts.

## Process

1. Identify the source set and freshness of each source.
2. Extract claims that matter to the user's decision.
3. Group claims by theme, not by source order.
4. Mark contradictions, missing evidence, and assumptions.
5. Separate confirmed facts from inference.
6. Capture source origin for important claims: `local repo`, `user-provided`, `read-only MCP`, `web`, `model inference`, or `assumption`.
7. If a visual artifact is likely, shape findings into sections an artifact can render: flows, comparison tables, source maps, risk panels, and next-step plans.

## Resource Gaps

- After the first source pass, ask for missing materials only if they change the decision: maps, screenshots, graphics, datasets, docs, pricing inputs, examples, or prior artifacts.
- Say what each requested resource would unlock.
- If the user points at an existing artifact, treat it as a source and identify what a follow-up artifact should deepen or revise.

## Output

- Lead with the answer or decision-relevant finding.
- Include citations for non-trivial claims.
- Use exact dates for current or time-sensitive claims.
- Add confidence levels when sources vary in quality or recency.
- Keep direct quotes short and only when wording matters.
- Make source origin visible when it affects trust or freshness.

## Decision Memo Format

Use this structure when the user asks for a recommendation:

1. Recommendation.
2. Why.
3. Evidence.
4. Risks or open questions.
5. Next action.

## Planning Handoff Format

Use this structure when the result should feed Claude, Codex, design, or implementation work:

1. Goal and success criteria.
2. Evidence-backed current state.
3. Proposed flows or artifact sections.
4. Pros, cons, risks, and assumptions.
5. Open questions or resources needed.
6. Next agent/task prompt.
