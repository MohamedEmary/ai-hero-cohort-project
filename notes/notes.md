# Oh My Pi Hotkeys

## Navigation

| Key                      | Action                                       |
| ------------------------ | -------------------------------------------- |
| Arrow keys               | Move cursor / browse history (Up when empty) |
| Option+Left/Right        | Move by word                                 |
| Ctrl+A / Home / Cmd+Left | Start of line                                |
| Ctrl+E / End / Cmd+Right | End of line                                  |

## Editing

| Key                        | Action                  |
| -------------------------- | ----------------------- |
| Enter                      | Send message            |
| Shift+Enter / Option+Enter | New line                |
| Ctrl+W / Option+Backspace  | Delete word backwards   |
| Ctrl+U                     | Delete to start of line |
| Ctrl+K                     | Delete to end of line   |
| Option+Shift+L             | Copy current line       |
| Option+Shift+C             | Copy whole prompt       |

## Other

| Key                                             | Action                                                               |
| ----------------------------------------------- | -------------------------------------------------------------------- |
| Tab                                             | Path completion / accept autocomplete                                |
| Esc                                             | Cancel autocomplete / interrupt active work                          |
| Ctrl+C                                          | Clear editor (first) / exit (second)                                 |
| Ctrl+D                                          | Exit (saves current prompt as draft)                                 |
| Ctrl+Z                                          | Suspend to background                                                |
| Option+L                                        | Reset terminal display                                               |
| Shift+Tab                                       | Cycle thinking level                                                 |
| Ctrl+P                                          | Cycle role models (slow/default/smol)                                |
| Shift+Ctrl+P                                    | Cycle role models (backward)                                         |
| Option+P                                        | Select model (temporary)                                             |
| Option+M                                        | Select model (set roles)                                             |
| Option+Shift+P                                  | Toggle plan mode                                                     |
| Ctrl+R                                          | Search prompt history                                                |
| Ctrl+O                                          | Toggle tool output expansion                                         |
| Ctrl+Shift+O                                    | Toggle tool activity visibility                                      |
| Ctrl+T                                          | Toggle thinking block visibility                                     |
| Ctrl+G                                          | Edit message in external editor                                      |
| Option+R                                        | Retry last failed assistant turn                                     |
| Ctrl+V/Cmd+V                                    | Paste image or text from clipboard                                   |
| Hold Space                                      | Speech-to-text (push-to-talk): hold to record, release to transcribe |
| Ctrl+L                                          | Start/stop live voice mode (`/live`)                                 |
| Option+A / Ctrl+S / double-tap ← (empty editor) | Open the agent hub                                                   |
| `#<number>`                                     | GitHub issue/PR reference (e.g. `#3164` → `pr:///issue://`)          |
| `#` / `#<text>`                                 | Prompt actions (copy / undo / move cursor)                           |
| `/`                                             | Slash commands                                                       |
| `!`                                             | Run bash command                                                     |
| `!!`                                            | Run bash command (excluded from context)                             |
| `$`                                             | Run Python in shared kernel                                          |
| `$$`                                            | Run Python (excluded from context)                                   |

# Some Commands

> Things that have this emoji 🚫 are not available in oh-my-pi, but are available in claude-code.

- `/context`
- `/clear`
- `/usage`
- `/resume`
- Ctrl + S: Stash a command and get it back after sending a message 🚫
- Ctrl + C: Clear the editor (first) / exit (second)
- `/ide`: Connects the agent to the IDE to see the diff in the editor instead of the terminal 🚫
- `esc + esc`: Rewind mode (undo the last message) 🚫
- `omp/claude --continue`: Continue the last conversation
- `!`: Run command in bash in claude/omp context
  - `Ctrl + b`: keep command running in the background 🚫. This allows u to have a window of running bg proccesses that the agent can interact with (e.g. debug an error in the dev server)
- Ctrl + Z and `fg`: Suspend the agent to background and bring it back to foreground. This allows you to run other commands in the terminal while the agent is running in the background.
  - omp does this better using `!!`
- Claude command permissions:
  - yes, yes and allow in this project, no
  - when pressing tab when being on the "no" option you can write the reason for example it asks to run `npm` while we use `pnpm` and you can write "we use pnpm" and it will remember that for the next time.
- Claude permissions per project/globally

```json
{
  "permissions": {
    "allow": ["Bash(npx tsc:*)", "Bash(pnpm *)", "WebSearch"],
    "deny": ["Bash(git push *)"]
  }
}
```

TODO: how to manage command execution, and permissions in general in omp, for things like web search for example
