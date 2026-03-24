---
name: investigate-and-plan
description: |
  This skill should be used when the user asks to "investigate and plan", "analyze and
  plan", "research then plan", or wants a structured investigation followed by an
  actionable plan using the OODA loop agents.
argument-hint: <subject>
disable-model-invocation: true
---

Plan:

<subject_to_plan>
$ARGUMENTS
</subject_to_plan>

Workflow: `@ooda:observe -> @ooda:orient -> @ooda:decide`. Output of observe goes to orient, then output goes to decide.

Use only @observe, @orient, and @decide subagents to create the plan. DO NOT make code changes. DO NOT execute any commands that will mutate state on my system. You SHALL ONLY create a plan to address.
