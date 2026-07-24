# Hypothesis Debugging

Agents are great at debugging — until they aren't. The problem: they scope around, get close to the root cause, then switch direction as new context comes in. By the time they've tried 3 things, context is bloated, they forget what they already disproved, and they're stuck in a loop or give you a wrong fix.

This skill fixes that by forcing a tight loop: **form one testable hypothesis → write it in HYPOTHESES.csv → run a single test to validate or invalidate it → write the conclusion → repeat**. Every hypothesis gets logged. Every conclusion is recorded. The agent can't forget what it tried because it's right there in the CSV.

No more spinning. No more lost context. Just iteratively narrowing in on the real root cause.

## Install

```bash
npx skills add ioma8/hypothesis-debugging
```

## License

MIT
