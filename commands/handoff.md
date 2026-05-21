Generate a complete session handoff document and save it to `CLAUDE-CODE-HANDOFF.md` in the current working directory. Overwrite any existing version.

Before writing, gather all of the following. Use read-only commands only (git, ls, cat) — do not modify files during this step.

---

**1. Git state**
- `git branch` — current branch
- `git status` — modified, staged, untracked files
- `git log --oneline -10` — last 10 commits
- `git diff HEAD` — full diff of all uncommitted changes
- `git log --oneline main..HEAD` or equivalent — commits ahead of main/master

**2. What was accomplished this session**
- Every meaningful change made during this conversation
- For each: which file, what changed, and why

**3. What is still pending**
- Every unfinished task, open TODO, or thing mentioned but not acted on
- If work was interrupted mid-way, describe exactly where it stopped

**4. Decisions and approach**
- The reasoning behind key decisions (WHY, not just what)
- Alternatives considered and rejected, and why

**5. Config and environment changes**
- Any config files modified during this session: `.env`, `package.json`, `tsconfig.json`, `settings.json`, CI/CD files, Dockerfiles, etc.
- The exact change and the reason for it

**6. Dependency changes**
- New packages installed (npm, pip, cargo, etc.) — name and version
- Packages removed or version-bumped
- Whether `package-lock.json` / `requirements.txt` / lockfile was updated

**7. Key files index**
- The most important files touched or relevant to current work
- One-line description of what each file does and its current state

**8. Known issues, gotchas, and workarounds**
- Bugs discovered (fixed or unfixed)
- Surprising behaviour, OS-specific quirks, or environment oddities
- Workarounds applied and why (so the next session doesn't undo them)

**9. Guardrails — what NOT to do**
- Specific things the next session must avoid changing
- Fragile areas, known regression risks, explicit user preferences

**10. Environment and running services**
- How to start the project (dev server, backend, DB, etc.)
- Required environment variables and where they are stored
- External services in use and their current state (e.g. Stripe test vs live mode, staging vs prod DB, API keys in use)
- Any background processes that need to be running

**11. Test state**
- Which tests currently pass and which fail
- Any tests skipped, marked xfail, or temporarily disabled
- How to run the test suite

**12. Context window note**
- If this session was long and earlier context may have been lost, say so explicitly
- List any key decisions or instructions from early in the conversation that must not be forgotten

**13. Memory and user preferences**
- Preferences or feedback the user expressed during this session
- Things said in chat that should inform future behaviour but aren't yet saved to memory files

**14. Next steps (prioritised)**
- Numbered list, most important first
- Each step specific enough to execute without needing to ask — include the exact file and what to do

---

Format the output as structured markdown with clear `##` headers matching the sections above.

**Open with a `## How to Start` section** — one sentence naming the single most important next action for the new session.

**Close with a `## Stack Snapshot`** — a concise block covering: tech stack, key directories, how to install deps, and how to run the project locally. Should be readable cold in under 30 seconds.
