# Scribble Remaining Work

## Done In Initial Scaffold

- Created a skills-first repo with three starter skills.
- Added Codex and Claude plugin manifests for marketplace compatibility.
- Added command shims for research and HTML discovery flows.
- Added install docs using `npx skills` as the primary cross-agent path.

## Still To Do

- Validate `npx skills add ./scribble --all -g` across all installed agents on this machine.
- Validate Codex marketplace install through `/plugins`.
- Validate Claude Code marketplace install through `/plugin`.
- Check Cursor, Gemini CLI, and OpenCode current plugin metadata before calling those surfaces stable.
- Add logo and screenshots before making the repo public.
- Publish the GitHub repo as `mpatino117/scribble` when the local install path is reliable.
- Add release notes and bump plugin versions when the first public release is ready.

## Future Skills

- `market-research` for startup/product market scans with fresh source dates.
- `architecture-discovery` for repo architecture maps and service flow diagrams.
- `competitor-landscape` for competitive research and positioning.
- `business-model-review` for pricing, unit economics, and risk review.

## Validation Commands

```bash
python3 -m json.tool .codex-plugin/plugin.json
python3 -m json.tool .agents/plugins/marketplace.json
python3 -m json.tool .claude-plugin/plugin.json
python3 -m json.tool .claude-plugin/marketplace.json
python3 -m json.tool .cursor-plugin/plugin.json
npx skills add ./scribble --list
npx skills add ./scribble -a codex -g
npx skills list -a codex
```
