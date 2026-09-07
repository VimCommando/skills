---
name: research
description: Investigate a question against high-trust primary sources and capture the findings as a Markdown file in the repo. Use when the user wants a topic researched, docs or API facts gathered, or reading legwork delegated to a background agent.
---

Define the research question, scope, and requested deliverable from the user's task. Separate answerable questions from decisions the user must make.

Spin up a **background agent** to do the research, so you keep working while it reads.

Give it the bounded question, relevant local sources, and output location. Its job:

1. Investigate the question against **primary sources** (official docs, source code, specs, first-party APIs), not a secondary write-up of them. Follow every claim back to the source that owns it.
2. Write the findings to a single Markdown file, citing each claim's source.
3. Save it where the repo already keeps such notes; match the existing convention, and if there is none, put it somewhere sensible and say where.

Complete when each scoped question has cited findings or an explicit evidence gap. Include conflicting evidence and limits. Return the absolute artifact path and unresolved questions to the parent so the research can be used in the ongoing task.
