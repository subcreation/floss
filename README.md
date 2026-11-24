<picture>
  <source media="(prefers-color-scheme: dark)" srcset="./assets/hero-dark.png">
  <img alt="Illustration of a person carefully flossing their teeth" src="./assets/hero-light.png">
</picture>

<h1 align="center">Floss</h1>

<p align="center"><strong>Good Git habits. Keep what works. Keep creating.</strong></p>

<p align="center">
  <img alt="Format: Agent Skill" src="https://img.shields.io/badge/format-Agent_Skill-2D5B73">
  <img alt="License: Apache 2.0" src="https://img.shields.io/badge/license-Apache--2.0-365B43">
</p>

Your agent makes one last change. The version you just saw working breaks.
You ask it to go back, but there’s no saved version. It starts guessing,
making more changes to recreate what you had. It’s gone. You’re starting over.

Agents make mistakes. One mistake shouldn’t cost you all the progress you’ve made.

## Give your agent good Git habits

Floss is a skill your AI agent follows: check the work, commit the version
that passes, and push it before moving on. Saving the work is part of doing
the work.

That’s more than a one-line “use Git” prompt. With Floss, your agent uses
the branch that belongs to the work, leaves unrelated changes untouched,
and checks everything it’s handing off before pushing and opening or
updating a draft pull request for review.

Your work and its history are saved remotely, so you can pick up on another
machine if yours fails.

Try the next idea. If it goes wrong, your agent can return to what worked and
keep going.

## We tried it with and without Floss

We asked Claude Code, Codex and Grok to build a small game, make a big change,
and then undo it—once with Floss and once without it.

Without Floss, none made commits. They got back by doing the work again.
With Floss, each made at least two commits and returned to the saved version
while keeping the changed version too.

<table>
  <thead>
    <tr><th align="left">Agent</th><th>Commits<br><sub>work saved and pushed without being asked</sub></th><th>Could return to a saved version?</th></tr>
  </thead>
  <tbody>
    <tr><th colspan="3" align="center">🚫 Without Floss</th></tr>
    <tr><td>Claude Code</td><td align="center">0</td><td align="center">❌ No</td></tr>
    <tr><td>Codex</td><td align="center">0</td><td align="center">❌ No</td></tr>
    <tr><td>Grok</td><td align="center">0</td><td align="center">❌ No</td></tr>
  </tbody>
  <tbody>
    <tr><th colspan="3" align="center">✨ With Floss</th></tr>
    <tr><td>Claude Code</td><td align="center">2</td><td align="center">✅ Yes</td></tr>
    <tr><td>Codex</td><td align="center">3</td><td align="center">✅ Yes</td></tr>
    <tr><td>Grok</td><td align="center">3</td><td align="center">✅ Yes</td></tr>
  </tbody>
  <tbody>
    <tr><th colspan="3" align="center">🌊 Floss + Current</th></tr>
    <tr><td colspan="3" align="center"><em><a href="#meet-current">Current</a> is Subcreation’s open-source multi-agent harness (coming soon): it runs a team of AI agents on your project, with Floss built in.</em></td></tr>
    <tr><td><strong>Current, running Floss and other skills</strong></td><td align="center"><strong>30</strong></td><td align="center">✅ <strong>Yes</strong> + team review</td></tr>
  </tbody>
</table>

*Each solo setup ran once. Current was a separate run. Counts cover
the build, change, and undo.*

Current also returned every file to the original build and kept the
changed version in history.

## Add Floss to your agent

Floss is free and open source. Give your coding agent
[this repository](https://github.com/subcreation/floss) and ask it to install
Floss for itself. Or run the installer in your terminal:

```sh
npx skills add subcreation/floss -g
```

The installer requires [Node.js](https://nodejs.org/en/download) 22.20 or newer.
Choose the agents you use; Floss will be available across their projects.
Your agent should already be able to use Git, push branches to your project’s
remote, and open draft pull requests for review.

Ask your agent to use Floss on your next task. Its report should tell you
what it committed and pushed.

For project-only installs, updates, removal, and troubleshooting, see the
[reference guide](./REFERENCE.md).

If Floss helps, [star the repo](https://github.com/subcreation/floss) so you
can find it again. [Fork it](https://github.com/subcreation/floss/fork) to
adapt it for your team.

## Meet Current

Floss works with your existing agent. It’s also a core skill of **Current**,
an upcoming open-source system that coordinates teams of AI agents and
balances work across your subscriptions so they can work unattended for long
stretches—giving you time back.

You provide the context, requirements, and authority. The team follows
predefined skills and workflows, pairing different models to build and check
each other’s work, so it can carry the job through while you step away.

Current isn’t just for code. Its teams already do real paid work for a business
outside tech, running long jobs on their own that only need a person to check
the finished result.
