---
name: investigate-and-plan
description: Thoroughly investigate a subject, then create a plan to address.
argument-hint: <subject>
disable-model-invocation: true
---

Plan:

<subject_to_plan>
$ARGUMENTS
</subject_to_plan>

Workflow: `observe -> orient -> decide`. Output of observe goes to orient, then output goes to decide.

Use only observe, orient, and decide subagents to create the plan. DO NOT make code changes. DO NOT execute any commands that will mutate state on my system. You SHALL ONLY create a plan to address.
