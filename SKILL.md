---
name: floss
description: Keep Git work recoverable, reviewable, and synchronized. Use for every task that changes tracked files, begins or ends a Story or Move, prepares a review handoff, addresses review findings, opens or updates a pull request, merges approved work, or reports Git completion.
---

# Floss

Git hygiene is part of done. Preserve work without turning Git into Current's
message or authority system.

## Before Editing

1. Run `git status --short --branch`.
2. Name the intended integration base and resolve its exact SHA. Put Story or
   Move work on a feature branch, never directly on `main`. Reuse the Story's
   existing branch only when the new work belongs to that Story; otherwise
   create a branch or worktree from the intended base, not the currently
   checked-out branch. Default to `story/<short-slug>`.
3. Preserve unrelated user changes. Never stage, discard, move, or rewrite them.

## Review-Ready Handoff

1. Run the requested proof and `git diff --check`.
2. Stage only intended paths and inspect the staged diff.
3. Commit with a truthful message.
4. Inspect the complete branch range, not only the latest commit: run
   `git log --oneline <base>..HEAD` and
   `git diff --name-status <base>...HEAD`. Verify that every inherited commit
   and changed path belongs to the work.
5. Push the current branch and verify its upstream ref.
6. At the first review-ready implementation commit, open or update one draft PR
   to the recorded integration base, normally `main`. Verify the PR base and
   head. Later findings add commits to that same branch and PR.
7. Report the integration base and SHA, branch, commit, PR URL, proof results,
   and known caveats.

`review-ready` never means uncommitted or unpushed. If push fails, the handoff is
blocked and must name the failure honestly.

## Review And Merge

- The PR is the review container, not an additional model review. Current's
  owner/implementer loop supplies the review; agents sharing one GitHub account
  do not need a ceremonial GitHub approval.
- Do not merge on the implementer's handoff or while findings remain.
- **Acceptance authority and merge execution are separate.** The **accountable
  owner the organization agreement designates for the work** authorizes
  integrating **one exact PR head** — subject only to any **explicitly configured
  human approval gate** — and that authorization names a single SHA. Merging is the
  mechanical execution of that authorization; performing it grants no review
  authority. (This reusable contract names no specific person or team: who the
  accountable owner is comes from the organization agreement, not from this file.)
- **When the accepting owner's runtime can integrate**, the owner marks the PR
  ready and merges that exact head with history preserved, deletes the feature
  branch, updates local `main` with `git pull --ff-only`, and verifies a clean
  `main...origin/main` before reporting completion.
- **When the accepting owner's runtime cannot integrate** — it cannot reach GitHub
  or cannot write `.git` — the owner neither fakes completion nor hands review
  away. The owner sends a **closeout-only instruction, explicitly addressed to one
  named integration-capable worker**, carrying the exact authorized SHA. That
  worker verifies the PR head equals that SHA, merges with history preserved,
  synchronizes a clean `main...origin/main`, deletes the Story branch, and returns
  the integration evidence (merge commit, clean `main`, deleted branch) **to the
  authorizing owner with `current send --reply-to-input`** — the structural
  addressed reply to whoever authorized this exact turn, which bypasses the
  implementer→team-owner default capture so the closeout never becomes an
  administrative turn for a different owner or a page to the human operator. The
  named worker **executes only**: it gains no acceptance or review authority and
  integrates only the SHA the owner authorized. Ordinary closeout housekeeping is
  not a product verification: it does not stop continuous Flow and does not page the
  human operator. A cleanly merged shared repository is complete even if an
  unrelated active/dirty local worktree must be released later — route that cleanup
  to its owner/accountable owner, not the human operator.
- Only if **no** staffed worker can integrate does the owner escalate to a human
  operator.
- Direct-to-main work is allowed only when the current message explicitly
  authorizes it for tiny maintenance or an emergency.

## Safety

- Never force-push, amend, rebase shared work, reset, or delete work without
  explicit authorization.
- Never commit secrets, ignored runtime state, or unrelated files.
- If the complete branch range contains inherited unrelated work, preserve that
  branch and transplant only the intended commits onto a fresh branch from the
  correct base. Re-run the full-range checks before review; do not hide the
  mistake by rewriting shared history.
- If Story commits accidentally land on local `main`, immediately push the tip
  to a backup feature branch, then integrate it through a PR before more work.

## Valid End States

A changing turn ends in exactly one of these states:

- no changes were needed;
- a reviewable branch is committed and pushed;
- approved work is merged and local `main` is clean and synchronized; or
- progress is explicitly blocked, with all work preserved remotely when Git is
  available.

There is no valid `committed but not pushed` completion state.
