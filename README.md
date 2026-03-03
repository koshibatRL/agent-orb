# agent-orb

ASCII 3D energy sphere for your terminal. Monitors AI agent activity in tmux and reacts.

![Python 3](https://img.shields.io/badge/python-3.8+-green)
![No Dependencies](https://img.shields.io/badge/dependencies-none-brightgreen)

## What it does

- Renders a rotating 3D sphere with fluid surface deformation in ASCII art
- Monitors tmux panes for running AI agents (Claude, Codex, etc.)
- Reacts to agent activity: rotation speed, pulse, surface turbulence increase
- Displays system stats: CPU, memory, uptime
- Displays Claude Code daily usage stats (messages, tool calls)
- Green color gradient via true-color (24-bit) ANSI escapes

## Activity states

| Agents | Status     | Effect                              |
|--------|------------|-------------------------------------|
| 0      | DORMANT    | Slow rotation, calm surface         |
| 1      | ACTIVE     | Moderate rotation, gentle pulse     |
| 2      | ENGAGED    | Fast rotation, visible turbulence   |
| 3+     | FULL POWER | Maximum speed, staccato jitter      |

## Requirements

- Python 3.8+ (no external dependencies)
- Terminal with true-color support (iTerm2, Kitty, Alacritty, etc.)
- tmux (for agent monitoring; works without it but shows DORMANT)

## Install

```bash
# Clone and symlink
git clone https://github.com/koshibatRL/agent-orb.git
ln -s $(pwd)/agent-orb/agent-orb ~/bin/agent-orb

# Or just copy
cp agent-orb/agent-orb ~/bin/
chmod +x ~/bin/agent-orb
```

## Usage

```bash
agent-orb
```

Press `Ctrl+C` to exit.

## How it works

- 3D sphere rendered via parametric surface sampling with z-buffer
- Surface texture from multi-octave 3D noise (no polar artifacts)
- Orthographic projection with character aspect ratio correction
- Fast sin/cos lookup tables (4096 entries) for performance
- Background thread for system stats (no render blocking)
- Wall-clock animation timing for consistent speed
- ~8 FPS target, ~20ms render time per frame
