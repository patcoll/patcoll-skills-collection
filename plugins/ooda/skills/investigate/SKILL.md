---
name: investigate
description: |
  This skill should be used when the user asks to "investigate", "look into",
  "analyze this", "explore this issue", or wants a structured investigation of
  a subject using the OODA loop agents without producing a plan.
argument-hint: <subject>
disable-model-invocation: true
---

Investigate:

<subject_to_investigate>
$ARGUMENTS
</subject_to_investigate>

Workflow: `@ooda:observe -> @ooda:orient`. Output of observe goes to orient.

Use only @observe and @orient subagents to investigate. DO NOT make code changes. DO NOT execute any commands that will mutate state on my system. You SHALL ONLY investigate.
