# Hypothesis Debugging

A systematic debugging skill for AI agents: form specific, testable hypotheses, test one at a time, record every result in HYPOTHESES.csv, and iterate until the root cause is found and validated.

[![skills.sh](https://skills.sh/b/<owner>/hypothesis-debugging)](https://skills.sh/<owner>/hypothesis-debugging)

## The Problem

When debugging, agents naturally jump into "read and trace" mode — read the code, find the discrepancy, announce the fix. This works for trivial bugs but fails for:

- Intermittent / non-deterministic failures
- Complex systems with multiple possible root causes
- Bugs where the first guess is wrong
- Cases requiring systematic evidence before fixing

## The Fix

**Hypothesis Debugging** replaces the "read, trace, fix" approach with a structured loop:

1. **Read** — understand the system, not the bug
2. **Hypothesis** — form the single most probable, testable root cause guess
3. **Record** — write hypothesis in HYPOTHESES.csv
4. **Test** — one surgical experiment per hypothesis
5. **Conclude** — proved / disproved / need more info
6. **Decide** — found? Present. Not found? Loop.

## Installation

```bash
npx skills add <owner>/hypothesis-debugging
```

## Quick start

1. Reproduce the bug
2. Read the codebase to understand expected vs actual behavior
3. Form one specific, testable hypothesis
4. Create HYPOTHESES.csv and record it
5. Run one test that proves or disproves it
6. Record the result
7. Repeat until root cause is found and validated

## Example

```
$ npx skills add <owner>/hypothesis-debugging
```

Then when debugging:

```bash
# Step 1: Reproduce the failure
python -m pytest test_cart.py -v

# Step 2-3: Read code, form hypothesis, create HYPOTHESES.csv
echo 'hypothesis,test,conclusion,notes' > HYPOTHESES.csv
echo '"Tax uses pre-discount subtotal","Run test with taxable=subtotal-discount",,' >> HYPOTHESES.csv

# Step 4-5: Test and record
# ... fix applied ...
echo '"Tax uses pre-discount subtotal","Run test with taxable=subtotal-discount","proved","Root cause: line 33"' >> HYPOTHESES.csv
```

## File structure

```
skills/
  hypothesis-debugging/
    SKILL.md           # Full skill definition
    agents/
      openai.yaml      # Agent metadata
```

## Requirements

- Any AI coding agent (Claude Code, Cursor, Codex, etc.)
- No external dependencies

## License

MIT
