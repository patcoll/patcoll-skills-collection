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

Workflow: `observe -> orient`. Output of observe goes to orient.

Use only observe and orient subagents to investigate. DO NOT make code changes. DO NOT execute any commands that will mutate state on my system. You SHALL ONLY investigate.
