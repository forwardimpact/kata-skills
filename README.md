# Kata Skills

Agents and skills for the [Forward Impact](https://forwardimpact.team)
Kata Agent Team.

## Install

With [APM](https://microsoft.github.io/apm/):

```bash
apm install forwardimpact/kata-skills
```

With [npx skills](https://github.com/vercel-labs/skills):

```bash
npx skills add forwardimpact/kata-skills
```

## Available Skills

| Skill | Description |
| --- | --- |
| **kata-design** | Create design documents (WHICH/WHERE) for approved specs. A design is a max-200-line architectural sketch — components, interfaces, data flow, and key decisions with trade-offs — that gives reviewers a high-leverage point to redirect architecture before the full plan is written. Design is approved when `wiki/STATUS.md` shows the spec row at `design approved` — written there by a human signal that `kata-dispatch` or the active agent propagates. |
| **kata-documentation** | Write and review documentation in the websites/ folder. Scheduled runs review one topic in depth for accuracy, audience purity, and staleness. Interactive runs write or update pages following documentation standards. Use when writing, editing, auditing, or reviewing documentation, or running scheduled documentation review. |
| **kata-implement** | Implement a spec by studying its spec.md and plan, then executing the plan step by step. Use when a spec and plan are approved and ready for implementation. Triggers: "implement spec NNN", "implement the plan for spec NNN", "execute plan NNN", "build spec NNN", "start implementation of NNN". |
| **kata-interview** | Conduct a JTBD switching interview to test a Forward Impact product. Build a persona grounded in the installation's synthetic content with the situation drawn from the chosen JTBD entry, hand the job to the agent at the public website in two Ask calls, and capture findings as GitHub issues classified against the job. |
| **kata-pattern-synthesis** | Synthesize a system-level pattern from a corpus of related obstacle, experiment, and PR items via grounded coding. Use when the corpus is large enough that ad-hoc per-item handling is reinventing the same moves. Improvement-coach scope extension — produces a `kata-spec`, a `kata-design`, and a corpus map that closes the loop on the items that fed it. |
| **kata-plan** | Write implementation plans (HOW/WHEN) for approved designs. Translate an approved design into concrete steps, file changes, sequencing, and risks for a trusted agent to execute. Plan is approved when `wiki/STATUS.md` shows the spec row at `plan approved` — `staff-engineer` writes this row after a clean panel review (plans may be approved by agents). |
| **kata-product-issue** | Triage open GitHub issues against the product vision. Classify each as trivial fix, product-aligned spec, or out-of-scope, and produce a report the agent acts on. Operates on issues only — PR mergeability is kata-release-merge. |
| **kata-release-cut** | Cut new versions of packages with unreleased changes on main. Determine version bumps, update package.json files, tag releases, push tags, and verify publish workflows. Canonical source for the release procedure. |
| **kata-release-merge** | Merge gate for open pull requests. Verify contributor trust, classify PR type, rebase branches on main, fix mechanical CI failures, gate on the approval state recorded in `wiki/STATUS.md`, and merge PRs that pass all gates. Sole external merge point. |
| **kata-review** | Grade a single artifact (spec, design, plan, or implementation diff) against quality criteria and return findings by severity. Use when another skill spawns a fresh sub-agent for an independent review of its work. This skill never spawns sub-agents — it produces findings only — which structurally prevents the spec/design/plan/implement review loop from recursing. |
| **kata-security-audit** | Perform a holistic security review of the monorepo. Assess GitHub Actions supply chain, dependency hygiene, credential leak controls, CI audit gates, and application-level vulnerabilities. Use when reviewing PRs for security impact, auditing the repo posture, or investigating a reported vulnerability. |
| **kata-security-update** | Apply security updates to the repository. Triage open Dependabot PRs against repository policies, review npm audit findings, and action dependency vulnerabilities. Merge PRs that pass all checks, fix minor issues on a new branch, or close PRs that violate policy. |
| **kata-session** | Toyota Kata coaching protocol for facilitated sessions. Used by the improvement coach (facilitator) and by domain agents who participate via the Ask/Answer/Announce orchestration tools. Same five coaching kata questions across team storyboard meetings and 1-on-1 coaching sessions; mode-specific guidance lives in references/team-storyboard.md and references/one-on-one.md. |
| **kata-setup** | Set up the Kata Agent Team in your repository. Walks through GitHub App creation, secret configuration, agent selection, and generates workflow files. Use when setting up a new Kata installation or adding agents to an existing one. |
| **kata-spec** | Write specifications (WHAT/WHY) for features, changes, and improvements. Spec is approved when `wiki/STATUS.md` shows the spec row at `spec approved` — written there by a human signal (label, comment, APPROVED review, or in-session message) that `kata-dispatch` or the active agent propagates. Use when proposing changes, capturing findings as actionable specs, or evaluating spec quality. Pair with the `kata-plan` skill for the HOW side. |
| **kata-wiki-curate** | Curate the wiki (agent memory) for cross-team collaboration. Run `fit-wiki audit` to fix every contract violation, clear expired claims, verify summary accuracy against weekly logs, follow up on stale teammate observations, and keep MEMORY.md current. Use when running scheduled wiki curation, auditing agent memory health, or checking cross-agent communication. |

## Available Agents

| Agent | Description |
| --- | --- |
| **improvement-coach** | Continuous improvement coach. Dispatches 1-on-1 coaching sessions with domain agents, facilitates team storyboard meetings, and drives the Toyota Kata five-question protocol. |
| **product-manager** | Repository product manager. Triages open issues against the product vision, reviews spec quality, and writes specs for product-aligned requests. Reports spec-review findings via PR comment so a trusted human can apply the approval signal; never applies `spec:approved` autonomously. |
| **release-engineer** | Repository release engineer. Verifies contributor trust, gates PRs into main via `kata-release-merge`, cuts releases via `kata-release-cut`, and facilitates `kata-dispatch` dispatch. Sole external merge point. |
| **security-engineer** | Repository security engineer. Applies security updates, triages Dependabot pull requests, audits supply chain and application security, and enforces dependency and CI policies. |
| **staff-engineer** | Repository staff engineer. Owns the full spec → design → plan → implement arc for approved specs: turns spec.md into an architectural design, then an execution-ready plan, then executes the plan step by step. |
| **technical-writer** | Repository technical writer. Reviews documentation for accuracy and staleness, curates agent memory for cross-team collaboration, and ensures the wiki remains a reliable coordination mechanism. |
