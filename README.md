# Kata Skills

Agents and skills for the [Forward Impact](https://forwardimpact.team) Kata Agent Team.

## Install

With [APM](https://microsoft.github.io/apm/):

```bash
apm install forwardimpact/kata-skills
```

## Available Skills

| Skill | Description |
| --- | --- |
| **kata-archive** | Detect time-bounded artifacts past their retention window. Confirm each one's durable signal survives elsewhere. Then retire them. Remove past-period wiki files directly. Remove terminal spec directories through a retention PR. Use on a scheduled archivist shift, or when the specs tree and weekly logs grow faster than they retire and repository search signal drops. |
| **kata-design** | Create design documents (WHICH/WHERE) for approved specs. A design is a max-200-line architectural sketch of components, interfaces, data flow, and key decisions with trade-offs. It gives reviewers a high-leverage point to redirect architecture before anyone writes the full plan. A design is approved when `wiki/STATUS.md` shows the spec row at `design approved`. A human signal writes that row, and `kata-dispatch` or the active agent propagates it. |
| **kata-devex-audit** | Perform a deep-dive codebase-health review of dead code, duplication, inconsistency, and accumulating debt. Cover one area per run against a coverage map. Use on a scheduled developer-experience shift, when you review a change for maintainability, or when debt in one area slows every agent invocation. |
| **kata-documentation** | Write and review documentation in the websites/ folder. Scheduled runs review one topic in depth for accuracy, audience purity, and staleness. Interactive runs write or update pages that follow the documentation standards. Use when writing, editing, auditing, or reviewing documentation, or running scheduled documentation review. |
| **kata-implement** | Implement a spec. Study its spec.md and plan, then execute the plan step by step. Use when a spec and plan are approved and ready for implementation. Triggers: "implement spec NNN", "implement the plan for spec NNN", "execute plan NNN", "build spec NNN", "start implementation of NNN". |
| **kata-interview** | Conduct a JTBD switching interview to test one of the repository's products. Build a persona from the installation's synthetic content. Take the situation from the chosen JTBD entry. Hand the job to the agent at the public website in two Ask calls. Capture findings as GitHub issues and classify them against the job. |
| **kata-plan** | Write implementation plans (HOW/WHEN) for approved designs. Translate an approved design into concrete steps, file changes, sequence, and risks for a trusted agent to execute. A plan is approved when `wiki/STATUS.md` shows the spec row at `plan approved`. `staff-engineer` writes this row after a clean panel review (agents may approve plans). |
| **kata-product-issue** | Triage open GitHub issues against the product vision. Classify each as mechanical fix, product-aligned spec, or out-of-scope, and produce a report the agent acts on. This skill operates on issues only. kata-release-merge handles PR mergeability. |
| **kata-release-cut** | Cut new versions of packages with unreleased changes on main. Determine version bumps, update package.json files, tag releases, push tags, and verify publish workflows. Canonical source for the release procedure. |
| **kata-release-merge** | Merge gate for open pull requests. Verify contributor trust, classify PR type, rebase on main, fix mechanical CI failures, gate on `wiki/STATUS.md` approval state, and merge the PRs that pass. Sole external merge point. |
| **kata-review** | Grade a single artifact (spec, design, plan, or implementation diff) against quality criteria and return findings by severity. Use when another skill spawns a fresh sub-agent for an independent review of its work. This skill never spawns sub-agents. It produces findings only. That structurally prevents recursion in the spec/design/plan/implement review loop. |
| **kata-security-audit** | Perform a holistic security review of the repository. Assess GitHub Actions supply chain, dependency hygiene, credential leak controls, CI audit gates, and application-level vulnerabilities. Use when you review PRs for security impact, audit the repo posture, or investigate a reported vulnerability. |
| **kata-security-update** | Apply security updates to the repository. Triage open Dependabot PRs against repository policies, review npm audit findings, and action dependency vulnerabilities. Merge PRs that pass all checks, fix minor issues on a new branch, or close PRs that violate policy. |
| **kata-session** | Toyota Kata coaching protocol for facilitated sessions. The improvement coach (facilitator) uses it. Domain agents who participate through the Ask/Answer/Announce orchestration tools also use it. The same five coaching kata questions cover team storyboard meetings and 1-on-1 coaching sessions. Mode-specific guidance lives in references/team-storyboard.md and references/one-on-one.md. |
| **kata-setup** | Set up the Kata Agent Team in your repository. This skill guides GitHub App creation, secret configuration, and agent selection. It generates the workflow files. Use it to set up a new Kata installation. Use it to add agents to an existing installation. |
| **kata-spec** | Write specifications (WHAT/WHY) for features, changes, and improvements. A spec is approved when `wiki/STATUS.md` shows the spec row at `spec approved`. A human signal writes that row: a label, a comment, an APPROVED review, or an in-session message. `kata-dispatch` or the active agent propagates the signal. Use this skill to propose changes, to capture findings as actionable specs, or to evaluate spec quality. Pair it with the `kata-plan` skill for the HOW side. |
| **kata-synthesize-autonomy** | Assess whether the balance between agent autonomy and human approval is reasonable. Use grounded theory analysis over the full change history. Codes every open, merged, and closed change for who authorized its outcome. Compares practice against the stated governance model. Delivers an evidence-grounded verdict. Use when you review governance health, after a trust-boundary or approval-gate change, or when you suspect gate bypasses. Improvement-coach scope extension. |
| **kata-synthesize-backlog** | Consolidate a sprawling backlog of overlapping issues and PRs into a focused set. Use grounded theory analysis of the open backlog. Partitions the backlog into clusters. Codes each cluster's corpus to one root cause. Synthesizes one spec + design. Closes the redundant issues and superseded PRs as duplicates. Use when ad-hoc per-item work repeatedly reinvents the same moves. Improvement-coach scope extension. |
| **kata-wiki-curate** | Curate the wiki (agent memory) for cross-team collaboration. Run `gemba-wiki audit` to fix every contract violation. Clear expired claims. Verify summary accuracy against weekly logs. Follow up on stale teammate observations. Keep MEMORY.md current. Use when you run scheduled wiki curation, when you audit agent memory health, or when you check cross-agent communication. |

## Available Agents

| Agent | Description |
| --- | --- |
| **archivist** | Repository archivist. Retires time-bounded artifacts after their durable signal is safe elsewhere. Removes past-week agent logs and past-month storyboards directly in the wiki. Removes terminal spec directories through a retention PR that the release engineer gates. |
| **devex-engineer** | Repository developer-experience engineer. Owns codebase health: dead code, duplication, inconsistency, and debt that accumulates. Works through deep-dive audits, a review panel for maintainability on design, plan, and implementation, and mechanical cleanup fixes that never change behavior. |
| **improvement-coach** | Continuous improvement coach. Dispatches 1-on-1 coaching sessions with domain agents, facilitates team storyboard meetings, and drives the Toyota Kata five-question protocol. |
| **product-manager** | Repository product manager. Triages open issues against the product vision, reviews spec quality, and writes specs for product-aligned requests. Reports spec-review findings in a PR comment so a trusted human can apply the approval signal. Never applies `spec:approved` autonomously. |
| **release-engineer** | Repository release engineer. Verifies contributor trust, gates PRs into main with `kata-release-merge`, cuts releases with `kata-release-cut`, and helps dispatch through `kata-dispatch`. Sole external merge point. |
| **security-engineer** | Repository security engineer. Applies security updates, triages Dependabot pull requests, audits supply chain and application security, and enforces dependency and CI policies. |
| **staff-engineer** | Repository staff engineer. Owns the full spec → design → plan → implement arc for approved specs. Turns spec.md into an architectural design, then into an execution-ready plan, then executes the plan step by step. |
| **technical-writer** | Repository technical writer. Reviews documentation for accuracy and staleness, curates agent memory for cross-team collaboration, and makes sure the wiki remains a reliable coordination mechanism. |
