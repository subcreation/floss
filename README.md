<picture>
  <source media="(prefers-color-scheme: dark)" srcset="./assets/hero-dark.png">
  <img alt="Illustration of a person carefully flossing their teeth" src="./assets/hero-light.png">
</picture>

# Floss

**Your work arrives intact, reviewable, and ready to merge.**

![Format: Agent Skill](https://img.shields.io/badge/format-Agent_Skill-2D5B73)
![License: Apache 2.0](https://img.shields.io/badge/license-Apache--2.0-365B43)

Floss gives coding agents a repeatable Git handoff discipline: preserve
unrelated work, branch from the intended base, audit the complete branch, and
finish at an exact pushed or merged state.

The recognizable failure is deceptively ordinary: an agent says the task is
done, but its commit began on the wrong branch, includes somebody else's work,
exists only on one machine, or points at a pull request whose head no longer
matches what was reviewed.

```sh
npx skills add subcreation/floss -g
```

The Agent Skills installer detects compatible clients and lets the user choose
where to install Floss. Separate backend-specific commands are not required.

## Evidence

> **Benchmark in progress.** This panel will compare **review-ready on the
> first handoff** using the same task, model, effort, tools, and starting state
> with and without Floss. Until the fixtures, raw runs, and reproduction steps
> are published, this project claims no efficacy percentage.

The planned corpus, scoring gate, telemetry, and collection status are in
[benchmarks/README.md](./benchmarks/README.md).

**Field record** (observational, not a benchmark)

From Current's private repository, July 20 to October 4, 2026: all 77 changes
that reached `main` landed as merge commits from pull requests, with no direct
pushes and no force-pushes to `main`. Of the 17 pull requests closed without
merging in that repository, 16 still keep their history on a branch or archive
tag. This says nothing yet about review-readiness on the first handoff, which
the benchmark will measure. These are field observations from private team
records, not a controlled with/without comparison.

## Before And After

Without a handoff discipline:

```text
Agent: Done. I committed the fix.
Reality: wrong base, unrelated path staged, no upstream, no reviewable head.
```

With Floss:

```text
base:   main @ <exact-sha>
branch: story/<short-slug>
range:  every commit and changed path audited
head:   <exact-sha>, committed and pushed
review: draft PR base and head verified
state:  unrelated work preserved
```

## How It Works

1. **Orient before editing.** Inspect the worktree, name the intended base, and
   create or reuse only the branch that belongs to the work.
2. **Preserve before cleaning.** Never stage, discard, move, or rewrite
   unrelated work to make the repository look tidy.
3. **Audit the whole handoff.** Check the complete base-to-head commit and path
   range, not merely the latest diff.
4. **Finish where another person can continue.** Push the exact reviewed head,
   verify its upstream and pull request, or report the literal blocker.

## Guardrails

- No lost or silently discarded work.
- No unrelated changes hidden in the branch range.
- No feature work begun from an accidental base.
- No force-push, shared-history rewrite, or destructive cleanup by default.
- No claim of `review-ready` for an uncommitted or unpushed head.
- No merge without authority for one exact head.

## Philosophy

Git hygiene is part of done. A handoff that exists only in one agent's local
checkout is not a handoff, and a clean-looking branch created by destroying
context is not clean. Floss favors preservation over cosmetic tidiness and
exact repository state over reassuring language.

## Current-Specific Boundary

Most of Floss is portable Git discipline. The frozen skill also contains one
closeout route for Current, an open-source multi-agent harness (coming soon):
when the accepting owner cannot perform an authorized merge, a named
merge-capable worker returns evidence through `current send --reply-to-input`.

Outside Current, that command and routing contract are unavailable. Do not
invent a host-neutral equivalent or treat another agent's merge as review
authority. This section is Floss's explicit compatibility boundary: outside
Current, the accountable owner performs the authorized merge or hands it back
to a human.

## Installation

Install globally for every compatible agent the installer detects:

```sh
npx skills add subcreation/floss -g
```

Omit `-g` to install into the current project instead. To list the skill
without installing it:

```sh
npx skills add subcreation/floss --list
```

To install from a local clone:

```sh
git clone https://github.com/subcreation/floss.git
npx skills add ./floss -g
```

## Update

```sh
npx skills update floss -g -y
```

For reproducible setups, pin a tagged release instead of following the default
branch, for example:

```sh
npx skills add https://github.com/subcreation/floss/tree/v0.1.0 -g
```

## Uninstall

```sh
npx skills remove floss -g -y
```

## Compatibility

Floss is packaged as a root Agent Skill with optional OpenAI interface
metadata. Before release, the packaging candidate recorded this mechanical
evidence:

| Host | Packaging verification |
| --- | --- |
| Codex | Root discovery and isolated global install, source-tracked update, and uninstall passed. |
| Claude Code | Root discovery and isolated global install, source-tracked update, and uninstall passed. |
| Grok Build | Root discovery, native `grok inspect` discovery, source-tracked update, and uninstall passed; Floss behavior has also been exercised through Current. |

These checks prove package placement and lifecycle, not that every Floss
behavior has been exercised on all three supported hosts. Other Agent Skills
clients may discover the root `SKILL.md`, but remain unverified.

The skill expects Git and, for the review route, a GitHub-compatible pull
request workflow. The Current-specific closeout path additionally expects the
Current CLI and organization contract described above.

## Troubleshooting

**Floss refuses to call the work review-ready.** Confirm that the intended base
is named, the complete branch range contains only intended work, the current
head is pushed, and the pull request base and head match.

**The worktree contains somebody else's edits.** Preserve them. Do not stage,
stash, reset, move, or delete them merely to finish your task.

**A non-Current host reaches the Current closeout route.** Stop at the stated
compatibility boundary. Do not substitute an unreviewed routing mechanism.

## Project

- Read the [roadmap](./ROADMAP.md).
- Inspect or contribute to the [benchmark plan](./benchmarks/README.md).
- Read [CONTRIBUTING.md](./CONTRIBUTING.md) before proposing a behavior change.
- Review the portfolio [art direction](./assets/ART_DIRECTION.md).

Floss was built alongside Current, an open-source multi-agent harness (coming
soon).

Floss is licensed under the [Apache License 2.0](./LICENSE).
