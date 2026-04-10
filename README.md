# claude-statusline

Minimalist Claude Code statusline — dot progress bars, muted colors, clean layout.

Forked from [kamranahmedse/claude-statusline](https://github.com/kamranahmedse/claude-statusline).

```
/my-project  Sonnet 4.6
context ··········  12%
current ··········  38% → 14:30
week 5% → april 17, 18:00
extra $8.90/$10.00
```

**What's different:**
- Dot bars `·` instead of circles `●○`
- Muted color palette — color only where it matters (context load thresholds)
- Model name formatted as `Sonnet 4.6` instead of `claude-sonnet-4-6`
- Directory + model on one line
- Week and extra usage as plain text, no bar clutter
- 24-hour time, full month names
- Effort level removed — not reliably available yet (tracking [anthropics/claude-code#40261](https://github.com/anthropics/claude-code/issues/40261))

## Install

```bash
node bin/install.js
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
node bin/install.js --uninstall
```

Restores from backup if one exists, otherwise removes the script and cleans up settings.

## License

MIT © Anastasiia Anfimova
