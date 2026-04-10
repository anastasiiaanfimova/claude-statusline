# TODO

## Effort level display

Effort level (`low`, `medium`, `high`, `max`) currently not shown in statusline
because Claude Code does not expose it in the stdin JSON payload.

Currently removed from display to avoid showing a misleading hardcoded value.

**Watch these issues — when fixed, read `.effort` from stdin JSON:**
- anthropics/claude-code#40261 — Status line: show current effort/reasoning level
- anthropics/claude-code#38476 — Add effort level to statusline JSON input

**When resolved**, update `bin/statusline.sh`:
```bash
# Replace the settings.json fallback with:
effort=$(echo "$input" | jq -r '.effort // empty')
[ -z "$effort" ] && effort=$(jq -r '.effortLevel // empty' "$HOME/.claude/settings.json" 2>/dev/null)
[ -z "$effort" ] && effort="default"
```
Then add back to `line1`: `line1+=" ${dim}- ${effort}${reset}"`
