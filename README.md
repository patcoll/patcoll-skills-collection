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
```

## Plugins

### ooda

OODA loop agents (observe, orient, decide, act) for structured problem-solving. Includes investigation skills that coordinate the agents.

### find-tests

Finds tests relevant to changed files by tracing the call graph 3 layers deep. Includes a `find-and-run-tests` skill that discovers and runs all tests for the current branch.
