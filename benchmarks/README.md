# Floss Benchmark Plan

Status: **planned; no efficacy result has been published**.

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

## Publication Gate

No percentage, savings claim, or comparison chart may appear in the README
until this directory contains:

- versioned fixtures;
- machine-readable raw runs;
- scoring code;
- reproduction instructions;
- model, effort, host, and tool provenance; and
- an independent verification of the reported aggregation.

The README placeholder is the only approved evidence panel until that gate
passes.
