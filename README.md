# pi-plan-mode

Plan mode extension for pi — read-only exploration mode with plan creation and execution progress tracking.

> **中文文档**：[README.zh-cn.md](./README.zh-cn.md)

## Features

- **Read-only Exploration Mode**: Restricts tools to read-only commands (read, grep, find, ls, etc.), disables edit/write operations
- **Safe Bash**: Only allowlisted read-only commands are permitted; blocks destructive operations like rm, mv, git push, npm install
- **Plan Creation**: AI agent automatically extracts numbered steps from "Plan:" sections in responses
- **Progress Tracking**: Use `[DONE:n]` markers during execution to track step completion; UI shows progress (`☐ / ☑`)
- **Execution Mode**: Switch to full tool access upon user confirmation, execute steps one by one
- **Keyboard Shortcuts**: `Ctrl+Alt+P` to toggle plan mode; `Tab` in empty editor for quick toggle
- **Persistent State**: Restores plan state and completed steps across session resumes

## Installation

```bash
# Install from local path
pi install ~/Projects/pi-plan-mode

# Enable plan mode on startup
pi --plan
```

## Usage

1. Press `Ctrl+Alt+P` to enter plan mode (or use the `/plan` command)
2. The AI agent will only use read-only tools to explore the codebase
3. The agent's response should include a "Plan:" header with numbered steps
4. The extension presents action choices: Execute the plan / Stay in plan mode / Refine the plan
5. Choosing "Execute the plan" switches to full tool access for step-by-step execution
6. During execution, add `[DONE:1]`, `[DONE:2]`, etc. in responses to mark steps complete

### Commands

| Command  | Description               |
|----------|---------------------------|
| `/plan`  | Toggle plan mode          |
| `/todos` | Show current plan progress |

### Keyboard Shortcuts

| Shortcut      | Description                         |
|---------------|-------------------------------------|
| `Ctrl+Alt+P`  | Toggle plan mode                    |
| `Tab`         | Toggle plan mode when editor is empty |

## Development

```bash
# Build (tsc type check)
npm run build

# Type check
npm run typecheck
```

## License

MIT
