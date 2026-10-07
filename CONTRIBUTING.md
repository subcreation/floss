# Contributing To Floss

Floss should become stricter only when a reproduced Git handoff failure proves
that its current contract is insufficient.

## Useful Contributions

- A minimal repository fixture that reproduces a real handoff failure.
- A scoring or drift check that makes an existing rule mechanically visible.
- A non-destructive correction that preserves unrelated work.
- A verified adapter for an Agent Skills host.
- Clearer documentation that does not change the frozen behavior contract.

## Before Opening A Pull Request

1. Start from the intended integration base on a feature branch.
2. Keep unrelated work out of the branch.
3. Explain the failure class or documentation gap being addressed.
4. Include the smallest proof that would fail before the change and pass after
   it, when behavior changes.
5. Run `git diff --check` and inspect the full base-to-head commit and path
   range.
6. Push the exact head and open a draft pull request.

Changes to `SKILL.md` require a compatibility decision and independent review.
Do not add ceremony, dependencies, or host-specific behavior without a
demonstrated failure it resolves.

By submitting a contribution, you agree that it may be licensed under this
repository's Apache License 2.0.
