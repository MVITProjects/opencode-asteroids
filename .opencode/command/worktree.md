---
description: Create a git worktree under .worktrees/ named from the given context
---

Create a git worktree from the following context:

"$ARGUMENTS"

Rules:
- The context may contain spaces. Derive a short, descriptive, lowercase
  kebab-case directory name from it (e.g. "fix the collision detection bug"
  → fix-collision-detection). The worktree name must not contain spaces.
- If the context above is empty, reply that an argument is required
  (usage: /worktree <description>) and do nothing else.
- Otherwise run exactly one command, substituting the name you derived:

  git worktree add .worktrees/<name>

- Do nothing else: do not change directories, do not create branches
  manually, do not commit, do not run any other git command. Only run the
  command above and report its output.
