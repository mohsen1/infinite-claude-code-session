# Run Claude Code forever

1. make sure you have `tmux` installed
2. Update what prompt you want to give to Claude Code when its done with a session in `.claude/settings.json`
3. start claude with `tmux new-session -s claude 'claude --dangerously-skip-permissions'`
