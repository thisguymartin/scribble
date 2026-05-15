---
name: tool-evaluation
description: Use when comparing libraries, APIs, SaaS tools, infra providers, frameworks, or developer tools for adoption, replacement, or production use.
---

# Tool Evaluation

Use this before recommending a tool or technology.

## Required Checks

- Current docs or release notes.
- Maintenance health: recent commits or releases, open issue load, maintainer activity, and bus factor signals.
- License and commercial constraints.
- Production adoption signals.
- Fit with the user's stack, especially Go and TypeScript unless another stack is specified.
- Pricing, free tier limits, and expected monthly cost.
- Deprecations, breaking changes, migration risk, and lock-in.

## Recommendation Shape

Use this structure:

1. Problem being solved.
2. Shortlist of options.
3. Comparison table.
4. Recommended default.
5. Risks and migration notes.
6. Confidence level with source quality.

## Defaults

- Prefer simple and cheap options that cover most of the need.
- Do not assume a deployment target. Ask or state the assumption when infrastructure choice matters.
- Do not suggest sending real customer data to third-party AI services.
- Clearly flag anything based on inference instead of verified sources.
