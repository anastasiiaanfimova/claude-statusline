# claude-statusline

> 📦 **Archived (2026-05).** No longer actively maintained.
>
> The original blocker for showing effort level (Claude Code did not expose `effort.level` in the stdin JSON) was resolved in **claude-code ≥2.1.x** — `effort.level` and `thinking.enabled` are now in the stdin payload. See [`TODO.md`](TODO.md) for the small patch to wire it up if anyone wants to fork and revive the project.

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
- Effort level removed — was a blocker (not in stdin JSON); **resolved in claude-code ≥2.1.x**, see [`TODO.md`](TODO.md) for the patch

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
