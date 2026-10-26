# Minecraft Project — always-on constraints

Everything else lives in on-demand skills. This file holds only what must never be missed
while working in this repository.

## Version — detect, never assume
Each project declares its own target, and local pins win over any default.
- Current scheme is **year-based** (`26.x`) → **Java 25 + Gradle 9+**.
- Legacy `1.21.x` receives no *new* versions but is still a live, supported target — the
  test server runs **Paper 1.21.11** → **Java 21 + Gradle 8**.
- Never call 1.21 "dead", and never assume 26.x — read the project's pin first.
- Tag knowledge by scope: `[all]`, `[26.2]`, `[1.21.11]`.

## Non-negotiables
- Target the **Paper API**, not Spigot/Bukkit. Purpur only if the project already does.
- Test **live** via RCON + the Mineflayer bot, asserting on returned state — the bot cannot
  see the game. Console output reaches the log file; chat does not.
- Prefix test output `[TEST]`, debug output `[DEBUG]`.
- **Never** modify a server that is not the designated testing server.
- MockBukkit cannot prove Folia thread-safety or real server bootstrap — verify live.
- Voice, comments, commit wording and design decisions follow **`05-house-style.md`** (rule 05, always
  loaded). Engine specifics stay in the skills: `mc-folia`, `mc-paper-gotchas`, `minecraft-plugin-dev`.

## This file is generated
Edit the canonical copy at `D:\Code\tools\templates\cline-rules\minecraft.md`, then run
`pwsh -File D:\Code\ai\scripts\sync-cline-rules.ps1` to push it to every project.
