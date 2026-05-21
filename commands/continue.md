Load the session handoff document and resume the previous session.

Steps:

1. Look for `CLAUDE-CODE-HANDOFF.md` in the current working directory.

2. **If the file exists:**
   - Read the entire file carefully.
   - Internalise all sections: what was done, what's pending, decisions made, guardrails, environment setup, next steps.
   - Then respond with a structured briefing in this format:

     ```
     ## Session resumed

     **Last worked on:** [one-line summary of what was being done]
     **Status:** [done / in progress / blocked]

     **Pending (in priority order):**
     1. [step 1 from the handoff's next-steps section]
     2. [step 2]
     ...

     **Guardrails active:**
     - [list anything the handoff says NOT to do]

     **Environment:**
     - [how to start the project]
     - [any env vars or services to be aware of]

     Ready. What would you like to tackle first?
     ```

3. **If the file does not exist:**
   - Tell the user: "No `CLAUDE-CODE-HANDOFF.md` found in the current directory (`[cwd]`). Either the previous session didn't generate one, or you're in a different directory. You can run `/user:handoff` at the end of a session to create one for next time."

4. **If the user wants to start fresh despite a handoff existing:**
   - Acknowledge it and move on. Do not keep referencing the old handoff unless the user asks.
