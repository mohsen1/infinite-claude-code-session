# Infinite Claude Code Session



https://github.com/user-attachments/assets/003379fe-e650-47ff-a6ca-b1d59e43eb3d



## Usage

1. Make sure you have `tmux` installed
2. Update the prompt you want to give to Claude Code when it's done with a session in `.claude/settings.json`
3. Start Claude with:
   ```bash
   tmux new-session -s claude 'claude --dangerously-skip-permissions'
   ```

## License

MIT
