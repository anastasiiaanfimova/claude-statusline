# TODO

> **Status (2026-05): repository archived.** The blocker below is resolved upstream. Patch is left here for anyone forking the project.

## Effort level display — RESOLVED upstream

Originally the effort level (`low`, `medium`, `high`, `xhigh`, `max`) was not shown because Claude Code did not expose it in the stdin JSON payload.

**Resolved in claude-code ≥2.1.x:** `effort.level` and `thinking.enabled` are now in the stdin JSON.

Tracking issues (now closed/addressed):
- anthropics/claude-code#40261 — Status line: show current effort/reasoning level
- anthropics/claude-code#38476 — Add effort level to statusline JSON input

**Patch for `bin/statusline.sh`** (if you fork and want to wire it back in):
```bash
# Read effort.level from stdin JSON
effort=$(echo "$input" | jq -r '.effort.level // empty')
[ -z "$effort" ] && effort=$(jq -r '.effortLevel // empty' "$HOME/.claude/settings.json" 2>/dev/null)
[ -z "$effort" ] && effort="default"
```
Then add back to `line1`: `line1+=" ${dim}- ${effort}${reset}"`

Valid values as of claude-code 2.1.x: `low`, `medium`, `high`, `xhigh` (Opus 4.7), `max`.
