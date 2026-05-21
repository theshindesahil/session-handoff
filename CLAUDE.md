# Global Claude Code Configuration

This file applies to every Claude Code session on this machine, across all projects.

---

## Session Continuity System

Two slash commands manage context transfer between sessions:

| Command | When to use |
|---------|-------------|
| `/user:handoff` | End of a session — generates `CLAUDE-CODE-HANDOFF.md` in the project root |
| `/user:continue` | Start of a session — loads the handoff doc and resumes where you left off |

### On every new session start

1. **Check silently** for a `CLAUDE-CODE-HANDOFF.md` file in the current working directory.
2. **If found:** Immediately tell the user:
   > "A handoff doc exists from a previous session. Run `/user:continue` to resume, or just start fresh."
3. **If not found:** Start normally, no mention needed.

Never load the handoff doc automatically without the user invoking `/user:continue` — the user may be starting something new in the same directory.

---

## General Preferences

- Ask before any `git push`, no exceptions.
- Prefer editing existing files over creating new ones.
- No trailing summaries at the end of responses — the user can read the diff.
- No emojis unless explicitly asked.
