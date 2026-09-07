---
name: implement
description: "Implement a piece of work based on a spec or set of tickets."
disable-model-invocation: true
---

Implement the user's spec, ticket, or agreed conversation plan.

1. Resolve the source and record the starting HEAD SHA and working-tree status before editing. Preserve unrelated existing edits and pass them as exclusions to review.
2. Call the Skill tool with "tdd" for behavior that benefits from tests, reusing the test interfaces already agreed in the source or session. Run relevant typechecks and focused tests during implementation, then the required suite at the end.
3. Call the Skill tool with "code-review" in working-tree mode against the recorded starting SHA. Include staged changes and in-scope untracked files, plus the source spec and exclusions.
4. Address supported review findings within scope. Recheck affected behavior after fixes; document any remaining finding and its reason. Completion requires every acceptance criterion to have evidence or an explicit unresolved status.
5. Commit only this task's changes to the current branch when implementation and required checks are complete. Report the commit, checks, and remaining limitations. Tracker updates and pull requests follow the user's requested scope.
