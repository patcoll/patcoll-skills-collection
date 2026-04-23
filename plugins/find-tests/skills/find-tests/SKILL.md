---
name: find-tests
description: |
  This skill should be used when the user asks to "find tests", "find relevant tests",
  "what tests should I run", "trace test dependencies", or wants to discover all test
  files related to given files or functions by tracing the call graph 3 layers deep.
argument-hint: <files-or-functions>
---

Find all test files that should be run for the given files or functions, by tracing usage through the call graph 3 layers deep.

<input>
$ARGUMENTS
</input>

DO NOT make code changes. DO NOT execute any commands that will mutate state. Only investigate and report.

## Process

### Step 0: Detect project conventions

Before tracing, determine:
- **Language and framework** (e.g., Elixir/Phoenix, Ruby/Rails, Python/pytest, JS/Jest, Go)
- **Test file naming** (e.g., `_test.exs`, `_spec.rb`, `test_*.py`, `*.test.ts`, `*_test.go`)
- **Test location** — co-located with source, or in a separate directory (`test/`, `spec/`, `__tests__/`, etc.)
- **Test runner command** (e.g., `mix test`, `rspec`, `pytest`, `jest`, `go test`)

Use these conventions throughout the remaining steps.

### Layer 1: Direct

Launch Haiku agents in parallel where possible. Each layer builds on the previous.

For each input file path:
- Find its corresponding test file using the project's naming and location conventions
- Read the file and extract its public function/method names
- Grep for those names across all test files

For each input function name:
- Grep for it across all test files

Collect: all discovered test files + all source files that reference these functions.

### Layer 2: Callers

For each NEW source file discovered in Layer 1 (not the original inputs):
- Find its corresponding test file
- Extract its public function/method names
- Grep for those identifiers across test files

Collect: all newly discovered test files + new source files referencing these functions.

### Layer 3: Callers of callers

Repeat the Layer 2 process for source files newly discovered in Layer 2.

### Rules

- Deduplicate at every step — do not re-process files already seen
- Use fully-qualified names where possible to reduce false positives
- Skip trivially common names (`get`, `new`, `create`, `update`, `delete`, `list`, `init`, `run`, `call`, `handle`) unless part of a distinctive compound name
- Check that test files actually exist before including them

## Output

1. A summary table: each test file, which layer found it, and what identifier linked it
2. The final deduplicated test runner command with all paths, ready to copy-paste
3. Any source files lacking corresponding tests (potential coverage gaps)
