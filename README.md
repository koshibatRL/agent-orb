<p align="center">
  <br>
  <br>
  <code>
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Xx&nbsp;x&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<br>
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;==+=++;+;;=+++==&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<br>
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;=+;:;:·::··:···::+;;;x&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<br>
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;;:·:··::·············::;+==&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<br>
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;;::::::::·········:::···::·==+==&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<br>
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;:::··::+:::·····.···:·······:·;+;+xX&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<br>
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;:·······:·:·+·+·::····:+;:+:···x;&nbsp;;+xx&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<br>
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;::···:::::····::::··:::;;;::······:=+Xx&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<br>
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;:::·:::::·····:::··:::;;;++;::·..···:++xx&nbsp;&nbsp;&nbsp;&nbsp;<br>
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;;:··:;;;:::···::····::;;;;+++;··...··:;;=x#&nbsp;&nbsp;&nbsp;&nbsp;<br>
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;::··:;;;::··········:::::;++;:···.·:··:;=xX&nbsp;&nbsp;&nbsp;&nbsp;<br>
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;;:·:;;;::·····..····:::::;;;······;····++=&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<br>
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;+;++::::··...·..·········::·.··:······:;+&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<br>
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;=++;&nbsp;·····..;······;.....·x··.········::+&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<br>
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;++;::;;·:::;;:::··:;·..x·::····:·:·;::+&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<br>
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;++;:::::···:··:··.;.·:+:;;···:···::;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<br>
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;;;;;:·::··:··:.:;:;:;;:;:·::·::;;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<br>
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;+;;;;:·::··::;:;+;+;+::;::;;;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<br>
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;=+++;+:::::;++;+:::;::;;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<br>
  </code>
  <br>
  <br>
  <strong>agent-orb</strong>
  <br>
  <em>A living energy sphere for your terminal.</em>
  <br>
  <br>
  <a href="#install"><img src="https://img.shields.io/badge/python-3.8+-333?logo=python&logoColor=white" alt="Python 3.8+"></a>
  <a href="#install"><img src="https://img.shields.io/badge/dependencies-zero-333" alt="Zero dependencies"></a>
  <a href="LICENSE"><img src="https://img.shields.io/badge/license-MIT-333" alt="MIT License"></a>
</p>

---

Real-time ASCII 3D sphere rendered in your terminal. Monitors AI agent processes running inside tmux and changes its behavior based on activity — calm when idle, turbulent when your agents are working hard.

Built with zero dependencies. Pure Python. Pure math.

## Demo

```
              ·         · ;
          .  :;:;;==+==x==+;:.
         ·· ;=+;:·· ·····:;++xx
        .  :;:··· ·  ·  ····:;+=x
       .· ::···  · ·   ·  ···::+=xX.
       ·····:··  · · · ·  · ····;+xXx
       · ····:;:··:·:··:···:;····:;+xx
      ·····::;+;;:::::::::;;++;::···:=xX
      ····:;;++;;::::::::;;++++;;:····;=X%
      ····:;+++;;::::::::;;++++;;:····;=x%
      ·····:;+++;;::::::;;+++;+;::····;=x
       ·····::;+;;::::::;;++;;::·····:+=x
       · ····::;;:·:;::·:;:;::··:···:;=x
        ·· ··::·:· :;··· ···::··  ···;+=X
         · · ::··  ·::·    ···: · ·:;+=.
          ·  ·;::·· ·;:·· ····:··::;+x
              :;;::··:::·····:::;;+x·
                =+;;;;:::::::;;;+.
                   x=+++;;;;++x
                             +

    CLAUDE TODAY  msgs:742  tools:318
    CPU [###-------]  28.4%  MEM [######----] 61.2%  UP 02:14:37
    PANES: 4  AGENTS: 1  STATUS: ACTIVE  14:32:08
```

## Features

- **3D fluid sphere** — Rotating ASCII sphere with organic surface deformation, rendered with a z-buffer and multi-octave 3D noise
- **Agent-aware** — Detects Claude / Codex processes in tmux panes by walking the process tree
- **System dashboard** — CPU, memory, uptime, and Claude Code daily usage (messages & tool calls parsed from session logs)
- **True-color** — Green gradient shading via 24-bit ANSI escapes (falls back gracefully on unsupported terminals)
- **Lightweight** — ~20ms render per frame at 8 FPS. No flickering. Background thread for stats collection
- **Zero dependencies** — Pure Python 3. No pip install needed

## How it reacts

| Agents detected | State | Visual |
|:-:|:-:|:--|
| 0 | `DORMANT` | Slow rotation, calm surface |
| 1 | `ACTIVE` | Moderate speed, gentle pulse |
| 2 | `ENGAGED` | Fast rotation, turbulent surface, staccato jitter |
| 3+ | `FULL POWER` | Maximum intensity |

## Install

```bash
git clone https://github.com/koshibatRL/agent-orb.git
cd agent-orb
chmod +x agent-orb

# Option A: symlink into PATH
ln -s "$(pwd)/agent-orb" /usr/local/bin/agent-orb

# Option B: copy
cp agent-orb ~/bin/
```

## Usage

```bash
agent-orb        # run it
# Ctrl+C to exit
```

Works best in a dedicated tmux pane alongside your AI agents:

```bash
tmux split-window -h 'agent-orb'
```

## Requirements

| Requirement | Notes |
|:--|:--|
| Python 3.8+ | No external packages |
| True-color terminal | iTerm2, Kitty, Alacritty, WezTerm, Ghostty |
| tmux | For agent detection. Runs without it (stays DORMANT) |

## Under the hood

The sphere is rendered using the same technique as [`donut.c`](https://www.a1k0n.net/2011/07/20/donut-math.html) — parametric surface sampling with orthographic projection and a z-buffer. On top of that:

- **4-layer 3D noise** for organic surface texture (large blobs → fine swirls)
- **Radius distortion** from noise values — the silhouette deforms like fluid
- **Character aspect ratio correction** (2.2:1) for proper circular shape
- **Fast sin/cos LUT** (4096 entries) — no `math.sin()` in the hot loop
- **Pre-computed color LUT** (256 entries) — no f-string allocation per pixel
- **Wall-clock animation timing** — consistent speed regardless of frame drops
- **Background stats thread** — subprocess calls never block the render loop

## License

MIT
