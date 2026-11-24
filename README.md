# Nexus for macOS

Nexus is a terminal workspace for AI coding agents. You talk to a **lead**
Claude Code session, which starts **workers** that run side by side. A
dashboard shows every worker's status, and a follow pane shows the one you
select, all in one terminal window. This repo holds only the signed releases;
the source is private.

**Download:** <https://github.com/ChrisBarberRiley/nexus-releases/releases/latest>
(`Nexus.dmg`; `Nexus.dmg.sha256` holds its SHA-256).

## Requirements

- macOS 12 or later, on Apple Silicon or Intel (the app is universal). It
  includes everything else Nexus needs, such as Node and the runtime.
- A terminal: **iTerm2** (<https://iterm2.com>) is recommended. tmux, WezTerm
  and Kitty also work.
- **Claude Code**: `curl -fsSL https://claude.ai/install.sh | bash`, then run
  `claude` once and log in.
- **Codex CLI** (optional): `npm install -g @openai/codex`, then `codex login`.

## Install and first run

1. Download **Nexus.dmg**, open it and drag **Nexus** onto **Applications**.
   Then eject the DMG and always open Nexus from Applications.
2. The app is signed with a Developer ID and notarized by Apple. The first
   time, macOS asks whether to open an app downloaded from the Internet.
   Click **Open**.
3. Nexus shows a setup checklist: your terminal, Claude Code, Codex, the
   optional `nexus` command and updates. **Fix…** helps with anything
   missing. **Continue** asks for a folder and opens the workspace.
4. macOS asks once whether Nexus may control your terminal app. Click **OK**.
   Nexus only uses this to open and arrange its own window.

After that, clicking Nexus reopens the workspace in the last folder.
Option-click it to choose another folder. `nexus doctor` shows the checklist
again at any time.

## Updates

Nexus checks this repo's releases about every 6 hours. You don't need a
GitHub account or login. When a new version is out, the dashboard and the app
offer to update. An update downloads `Nexus.dmg`, checks it against
`Nexus.dmg.sha256`, swaps the app in place and moves the old one to the
Trash. Running agent sessions are left alone. To check now, run
`nexus update --check`. To install from a terminal, run
`nexus update --install`.
