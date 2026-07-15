# claude-statusline

Minimalist Claude Code statusline — everything on one line, muted colors, middot separators.

Forked from [kamranahmedse/claude-statusline](https://github.com/kamranahmedse/claude-statusline).

```
/my-project (main) · Opus 4.8 (high) · context 178.7k / 1.0M (18%) · current 15% → 13:30 · week 21% → july 21, 6:00
```

**What's different:**
- Single-line layout — directory, branch, model, effort, context and rate limits all on one row, joined by `·` separators
- Context as `used / window (percent)` — e.g. `178.7k / 1.0M (18%)`; the window auto-follows `context_window_size` from stdin (200K or 1M)
- Muted color palette — labels and separators grey; color only where it matters (context / rate-limit thresholds)
- Model name formatted as `Opus 4.8` instead of `claude-opus-4-8`
- Effort level next to the model (`Opus 4.8 (high)`) — reads `effort.level` from stdin (claude-code ≥2.1.x), falls back to `effortLevel` in `settings.json`
- 24-hour time, full month names

## Install

```bash
npx @anastasiiaanfimova/claude-statusline
```

Backs up your existing statusline to `~/.claude/statusline.sh.bak` and configures `~/.claude/settings.json`.

## Requirements

- [jq](https://jqlang.github.io/jq/) — for parsing JSON
- curl — for fetching rate limit data
- git — for branch info

```bash
brew install jq
```

## Uninstall

```bash
npx @anastasiiaanfimova/claude-statusline --uninstall
```

Restores from backup if one exists, otherwise removes the script and cleans up settings.

## License

MIT © Anastasiia Anfimova
