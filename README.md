# Infinite Claude Code Session

https://github.com/user-attachments/assets/003379fe-e650-47ff-a6ca-b1d59e43eb3d

## How it works

Claude Code hooks support special exit codes:

- **Exit code 0** - stdout/stderr not shown
- **Exit code 2** - show stderr to model and continue conversation
- **Other exit codes** - show stderr to user only

By using `exit 2` and writing the continue prompt to stderr, Claude Code will automatically continue the session without needing tmux!

## Usage

### Option 1: Without tmux (recommended)

1. Copy `.claude/settings.json` to your project
2. Update the prompt in the `echo` command to customize what Claude continues with
3. Start Claude with:
   ```bash
   claude --dangerously-skip-permissions
   ```

### Option 2: With tmux (legacy)

If you prefer tmux for other reasons:

1. Update `.claude/settings.json` to use tmux:
   ```json
   {
     "hooks": {
       "Stop": [
         {
           "hooks": [
             {
               "type": "command",
               "command": "tmux send-keys -t claude 'Continue' && sleep 0.1 && tmux send-keys -t claude Enter"
             }
           ]
         }
       ]
     }
   }
   ```
2. Start Claude with:
   ```bash
   tmux new-session -s claude 'claude --dangerously-skip-permissions'
   ```

## License

MIT
