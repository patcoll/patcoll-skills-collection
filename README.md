# patcoll-skills-collection

Claude Code plugins and agents.

## Install

```
claude plugin marketplace add patcoll/patcoll-skills-collection
```

Then install individual plugins:

```
claude plugin install ooda
claude plugin install find-tests
claude plugin install explain-diff
```

## Plugins

### ooda

OODA loop agents (observe, orient, decide, act) for structured problem-solving. Includes investigation skills that coordinate the agents.

### find-tests

Finds tests relevant to changed files by tracing the call graph 3 layers deep. Includes a `find-and-run-tests` skill that discovers and runs all tests for the current branch.

### explain-diff

Generate rich, interactive explanations of code changes, diffs, branches, or PRs. Includes an `explain-diff-html` skill that produces a self-contained HTML file and an `explain-diff-notion` skill that creates a Notion page.
