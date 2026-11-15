# Floss reference

More installation options, workflow details, and troubleshooting.

[Return to the README](./README.md).

## Other installation options

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

Floss is licensed under the [Apache License 2.0](./LICENSE).
