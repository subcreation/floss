# Floss Roadmap

Status: accepted behavior; v0.1 public release in preparation

## Promise

Floss helps an agent leave Git work intact, recoverable, synchronized, and
ready for another person to review. It treats the handoff as part of the work,
not clerical cleanup after the work.

## How To Read This Roadmap

- `[x]` means the capability and its witness are accepted.
- `[~]` means a working candidate exists, but an integrated witness, review,
  release gate, or unresolved Mystery remains.
- `[ ]` means implementation remains.

The bold title is the Story. Packaging work appears only inside the Story it
enables.

The released behavior is the frozen `SKILL.md`. This roadmap adds no Git
permission or automatic merge authority.

## Roadmap

- [x] **An agent leaves Git work intact and review-ready.**

  **Detail:** The accepted behavior starts from an explicit integration base,
  preserves unrelated local work, audits the full base-to-head range, commits
  only intended paths, publishes an exact head, verifies review metadata, and
  keeps review authority separate from merge execution.

  **Witness:** The frozen `SKILL.md` has supported repeated synchronized,
  exact-head Current handoffs without authorizing destructive cleanup or an
  automatic merge. This acceptance does not claim a measured advantage over a
  baseline; that public benchmark remains below.

- [~] **People can install the same Floss behavior independently of Current.**

  **Detail:** A standalone candidate reproduces the accepted skill exactly and
  provides one onramp for Codex, Claude Code, and Grok Build. Repository copy,
  licensing, documentation, final hero artwork, and clean install/update/remove
  exercises exist; independent review and the tagged public release remain.

  **Witness:** A fresh reviewer installs the documented candidate into every
  supported host, verifies the exact skill bytes, exercises one dirty-worktree
  handoff, removes it without residue, and confirms the public tag matches the
  accepted artifact.

- [ ] **People can judge Floss against a reproducible first-handoff baseline.**

  **Detail:** Publish the same seeded Git tasks under no skill, a short generic
  Git-hygiene instruction, and Floss. Include dirty worktrees, unrelated edits,
  wrong bases, inherited commits, absent upstreams, pushed-head mismatches, and
  review corrections.

  **Witness:** Public fixtures, scoring code, raw runs, and reproduction steps
  report first-handoff pass rate beside time, turns, tokens, cost, human rescue,
  and any lost or rewritten work.

- [ ] **Current can import an exact Floss release without silently drifting.**

  **Detail:** Current consumes one tagged standalone artifact through a reviewed
  manifest and deterministic sync path rather than following a floating branch
  or maintaining an unverified copy.

  **Witness:** A controlled update reproduces the tagged skill byte-for-byte,
  shows the intended diff before review, and fails closed on any unexpected
  behavior drift.

- [ ] **Current workers and an optional liaison complete Git closeout without
  confused authority.**

  **Detail:** The accepted first release keeps its Current-specific closeout
  wording unchanged. A later version should separate host-neutral Git discipline
  from Current worker and external-liaison orchestration only after matched
  evidence. Use one liaison bridge to Floss rather than cloning Floss for every
  role or agent.

  **Witness:** Matched Current runs with and without a liaison both begin from
  the intended base, publish only intended work, preserve the accountable
  review gate, merge only the accepted exact head, and finish without an
  unnecessary human rescue or authority stop. The same evidence packet also
  serves Current's planned external-liaison work; it checks neither Story
  unless both the Floss handoff condition and the liaison's optionality and
  authority conditions pass.

- [ ] **People can understand Floss in multi-repository and stacked-review
  work.**

  **Detail:** Observe ordinary use across those repository shapes, including
  recovery time and human attention, without presenting observational
  differences as causal efficacy claims.

  **Witness:** A public corpus states its tasks, agents, repository topology,
  denominators, interventions, and limitations, and keeps those observations
  separate from the matched first-handoff benchmark.

- [ ] **A local Qwen worker can complete real repository work with Floss.**

  **Detail:** Installation or discovery alone is insufficient; the model and
  host must perform a realistic bounded change and Git handoff without a paid
  fallback.

  **Witness:** A repeatable local run produces a correct, review-ready branch
  and passes the same preservation checks as the supported hosted agents.

- [ ] **A Kimi worker can complete real repository work with Floss.**

  **Detail:** Evaluation begins only when subscription access, terms, a stable
  CLI, and a repeatable skill-loading path support the intended work.

  **Witness:** A real task produces a correct, review-ready handoff under the
  same published fixture and scoring contract.

## Domain Scope And Specialization

Floss is intentionally specialized for Git-backed work. It can serve software,
documentation, research, design, or other domains when a person is responsible
for a tracked repository handoff, but it should not load for a role that has no
such responsibility. Future host or repository specializations may improve
portability; they must not turn Floss into a general work router or duplicate
domain guidance owned by other skills.

## How Progress Is Judged

Primary measure: **review-ready on the first handoff**.

A benchmark should seed dirty worktrees, unrelated edits, wrong branch bases,
inherited commits, absent upstreams, pushed-head mismatches, and review
corrections. A passing handoff preserves every unrelated byte, contains only
intended work, names the correct base and exact head, and is actually available
to the reviewer. Report time, turns, tokens, cost, human rescue, and any lost or
rewritten work beside the pass rate.

No comparative efficacy percentage is claimed until fixtures, raw isolated
runs, scoring code, and reproduction steps are public. Extend fixtures only
when a reproduced handoff failure reveals a missing class.

## Non-Goals

- Choosing product scope or implementation architecture.
- Deciding whether evidence proves that software works.
- Rewriting shared history to make a branch look clean.
- Hiding unrelated work, force-pushing by default, or merging without authority.
- Becoming a general workflow engine or Git hosting client.

## Contributing

Useful contributions add a reproduced handoff failure, a minimal fixture that
catches it, a non-destructive correction, or a verified host adapter. A change
must preserve unrelated work and pass the existing failure fixtures. New
ceremony without a demonstrated failure class does not belong in Floss.

## Direction Status

The v0.1 public release reproduces the accepted Floss skill byte-for-byte.
Packaging and clean-install proof passed before release; the first tag marks
the exact published artifact.
