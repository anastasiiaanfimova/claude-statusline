# claude-statusline

Minimalist Claude Code statusline — dot progress bars, muted colors, clean layout.

Forked from [kamranahmedse/claude-statusline](https://github.com/kamranahmedse/claude-statusline).

![demo](https://raw.githubusercontent.com/anastasiiaanfimova/claude-statusline/main/.github/demo.png)

**What's different:**
- Dot bars `·` instead of circles `●○`
- Muted color palette — color only where it matters (context load thresholds)
- Model name formatted as `Sonnet 4.6` instead of `claude-sonnet-4-6`
- Directory + model on one line
- Week and extra usage as plain text, no bar clutter
- 24-hour time, full month names
- Effort level shown next to the model (`Opus 4.8 - high`) — reads `effort.level` from stdin (claude-code ≥2.1.x), falls back to `effortLevel` in `settings.json`

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
