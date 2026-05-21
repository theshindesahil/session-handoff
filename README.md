# Claude Code Dotfiles

Global Claude Code config — works on any machine, any account.

## What's here

| File | Installs to | Purpose |
|------|-------------|---------|
| `CLAUDE.md` | `~/.claude/CLAUDE.md` | Global preferences applied to every session |
| `commands/handoff.md` | `~/.claude/commands/handoff.md` | `/user:handoff` — generates a session handoff doc |
| `commands/continue.md` | `~/.claude/commands/continue.md` | `/user:continue` — loads the handoff doc and resumes |

## Install on a new machine

**Windows (PowerShell):**
```powershell
Copy-Item claude-dotfiles\CLAUDE.md "$env:USERPROFILE\.claude\CLAUDE.md"
Copy-Item claude-dotfiles\commands\* "$env:USERPROFILE\.claude\commands\" -Force
```

**Mac / Linux:**
```bash
cp claude-dotfiles/CLAUDE.md ~/.claude/CLAUDE.md
cp claude-dotfiles/commands/* ~/.claude/commands/
```

## Usage

```
End of session  →  /user:handoff   →  writes CLAUDE-CODE-HANDOFF.md
Start of session →  /user:continue  →  reads it and briefs you
```

On session start Claude will also silently check for `CLAUDE-CODE-HANDOFF.md` and nudge you if one exists.
