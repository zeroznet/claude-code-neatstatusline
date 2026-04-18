# claude-code-neatstatusline

Clean status line for Claude Code.

## What it does

- displays model name + effort level
- context window usage bar (▰▱, green → yellow → red based on usage)
- 5-hour rate limit bar with same color coding
- user@host · working directory path
- git branch name, staged/unstaged line counts, untracked file count
- ✓ indicator when repo is clean

## Setup

1. Download the script to `~/.claude/`:

```sh
curl -fsSL https://raw.githubusercontent.com/zeroznet/claude-code-neatstatusline/main/claude-code-neatstatusline.sh -o ~/.claude/statusline-command.sh
```

FreeBSD without `curl`:

```sh
fetch -q -o ~/.claude/statusline-command.sh https://raw.githubusercontent.com/zeroznet/claude-code-neatstatusline/main/claude-code-neatstatusline.sh
```

2. Add to `~/.claude/settings.json`:

```json
{
  "statusLine": {
    "type": "command",
    "command": "bash ~/.claude/statusline-command.sh"
  }
}
```

## Configuration

The script reads your effort level from `~/.claude/settings.json`:

```json
{
  "effortLevel": "high"
}
```

Supported values: `low`, `medium`, `high`, or any custom string.

## Files

- `claude-code-neatstatusline.sh` - the status line script

## License

Licensed under the BSD-2-Clause license. See LICENSE.
