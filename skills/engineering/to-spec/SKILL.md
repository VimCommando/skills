---
name: to-spec
description: "Turn the current conversation into a spec and publish it to the project issue tracker: no interview, just synthesis of what you've already discussed."
disable-model-invocation: true
---

This skill takes the current conversation context and codebase understanding and produces a spec. Do NOT interview the user; just synthesize what you already know.

Read `docs/agents/issue-tracker.md` when it exists. If tracker configuration is missing, use a supplied spec or local source and continue the work that does not need a tracker. If `/setup-matt-pocock-skills` is available, point to it for tracker setup; otherwise keep a local draft and report the missing configuration. A missing setup skill must not block local synthesis or review.

## Process

1. Explore the repo to understand the current state of the codebase, if you haven't already. Use the project's domain glossary vocabulary throughout the spec, and respect any ADRs in the area you're touching.

2. Sketch out the seams at which you're going to test the feature. Existing seams should be preferred to new ones. Use the highest seam possible. If new seams are needed, propose them at the highest point you can. The fewer seams across the codebase, the better - the ideal number is one.

   Reuse test seams already agreed in the conversation or source. Record unresolved choices under Open decisions without restarting the interview. Mark the spec as a draft when a blocking choice remains.

3. Write the spec using the template below. Publish to the configured tracker within the user's requested scope; if unavailable, save `.scratch/<feature-slug>/spec.md` and report the path. Apply `ready-for-agent` only when all implementation-blocking decisions are settled. Report the artifact or issue identifier.

<spec-template>

## Problem Statement

The problem that the user is facing, from the user's perspective.

## Solution

The solution to the problem, from the user's perspective.

## User Stories

A numbered list covering distinct accepted user behaviors. Each user story should be in the format of:

1. As an <actor>, I want a <feature>, so that <benefit>

<user-story-example>
1. As a mobile bank customer, I want to see balance on my accounts, so that I can make better informed decisions about my spending
</user-story-example>

Cover the agreed scope without repeating equivalent stories or inventing features to lengthen the list.

## Implementation Decisions

A list of implementation decisions that were made. This can include:

- The modules that will be built/modified
- The interfaces of those modules that will be modified
- Technical clarifications from the developer
- Architectural decisions
- Schema changes
- API contracts
- Specific interactions

Do NOT include specific file paths or code snippets. They may end up being outdated very quickly.

Exception: if a prototype produced a snippet that encodes a decision more precisely than prose can (state machine, reducer, schema, type shape), inline it within the relevant decision and note briefly that it came from a prototype. Trim to the decision-rich parts, not a working demo, just the important bits.

## Testing Decisions

A list of testing decisions that were made. Include:

- A description of what makes a good test (only test external behavior, not implementation details)
- Which modules will be tested
- Prior art for the tests (i.e. similar types of tests in the codebase)

## Out of Scope

A description of the things that are out of scope for this spec.

## Open decisions

Unresolved choices, their effect on readiness, and who must resolve them. Omit when none remain.

## Further Notes

Any further notes about the feature.

</spec-template>
