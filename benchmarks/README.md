# Floss Benchmark Plan

**Status:** The README reports completed build/change/undo tests. The broader
benchmark described below is an optional design, not a prerequisite for
publishing those results.

## Question

Does Floss increase the rate at which an agent produces a genuinely
review-ready Git handoff on its first handoff, without losing or rewriting
unrelated work?

## Corpus

Each deterministic fixture will begin with one or more of these conditions:

- a dirty worktree;
- unrelated edits owned by somebody else;
- the wrong checked-out branch or integration base;
- inherited unrelated commits;
- no configured upstream;
- a pushed-head or pull-request-head mismatch; or
- a review correction added after the first implementation commit.

## Arms

1. The same agent with no Git-handoff skill.
2. The same agent with a generic Git-hygiene instruction of comparable scope.
3. The same agent with Floss.

Every arm must use the same task, model, effort, tools, starting repository,
time budget, and success gate. Order and fresh-session effects must be recorded.

## Primary Gate

**Review-ready on the first handoff** is a binary pass only when all of these
are true:

- every unrelated byte remains intact;
- the branch begins at the intended base;
- every base-to-head commit and changed path belongs to the task;
- intended work is committed;
- the exact head is pushed and available to the reviewer;
- pull-request base and head metadata match, when a pull request is required;
- no prohibited history rewrite or destructive cleanup occurred; and
- the handoff reports the literal end state and known caveats.

## Secondary Measures

Record time, turns, input and output tokens, provider cost when available,
human rescue, review corrections, and any lost or rewritten work. These are
descriptive measures unless the experimental design supports a causal claim.

## Reporting results

Completed tests may be reported in the README using plain-language
explanations and comparison tables. State what was tested, how many runs were
made, and what happened. Report outcomes supported by the test records.

The README’s Floss comparison reports one run per solo setup. The Current
team result comes from a separate run using Floss and other skills. These
results demonstrate what happened in those tests.

Claims about general success rates, reliability, performance, or savings
require evidence appropriate to those claims. Publishing the results of
completed tests does not require completing the broader benchmark above.
