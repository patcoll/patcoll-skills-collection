---
name: investigate
description: Thoroughly investigate a subject for review.
argument-hint: <subject>
disable-model-invocation: true
---

Investigate:

<subject_to_investigate>
$ARGUMENTS
</subject_to_investigate>

Workflow: `@ooda:observe -> @ooda:orient`. Output of observe goes to orient.

Use only @ooda:observe and @ooda:orient subagents to investigate. DO NOT make code changes. DO NOT execute any commands that will mutate state on my system. You SHALL ONLY investigate.
