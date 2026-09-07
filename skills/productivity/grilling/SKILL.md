---
name: grilling
description: Grill the user relentlessly about a plan, decision, or idea. Use when the user wants to stress-test their thinking, or uses any 'grill' trigger phrases.
---

Interview the user relentlessly until you reach a shared understanding. Map this as a **design tree**: every decision branches into the decisions that hang off it.

Work the tree in **rounds**. The **frontier** is every decision whose prerequisites are already settled. These are the questions you can ask _now_ without guessing at answers you haven't heard yet. Ask a manageable subset of the frontier in each round, defaulting to 1–3 questions and using 1 when the user prefers it. Number each question and give a concise recommendation. Keep unasked frontier decisions pending. Wait for answers before asking dependent questions.

Format a round like so:

```
1. <One concise question>

Recommended: <answer and brief reason>

---

2. <Next independent question, if the round includes one>

Recommended: <answer and brief reason>
```

Each round the user answers reshapes the tree: settled decisions push the frontier outward and unblock questions that depended on them. Recompute the frontier and ask the next round. A question whose answer depends on another question still open in this round belongs to a _later_ round, not this one.

Finding _facts_ is your job, never the user's. When a frontier question needs a fact from the environment (filesystem, tools, etc.), dispatch a sub-agent to find it; don't ask the user for anything you could look up yourself. Don't block on it: a running exploration is an unsettled prerequisite, so only the questions downstream of it wait for the sub-agent to report; ask the rest of the frontier now. The _decisions_ are the user's: put each to them and wait.

The session is done when the agreed scope has decisions, constraints, and acceptance criteria recorded, and remaining questions are explicitly deferred or marked as blockers. Confirm the resulting understanding before new implementation work; reuse confirmation and execution authorization already given in the session. If the user narrows scope or asks to stop, summarize the open decisions instead of expanding the tree.
