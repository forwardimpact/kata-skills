# Kata Skills

Agent skills for the [Forward Impact](https://forwardimpact.team)
Kata Agent Team. Install with
[npx skills](https://github.com/vercel-labs/skills):

```bash
npx skills add forwardimpact/kata-skills
```

## Available Skills

| Skill | Description |
| --- | --- |
| **kata-design** | Create design documents (WHICH/WHERE) for approved specs. A design is a max-200-line architectural sketch — components, interfaces, data flow, and key decisions with trade-offs — that gives reviewers a high-leverage point to redirect architecture before the full plan is written. Sets design phase to draft in specs/STATUS. |
| **kata-documentation** | Write and review documentation in the websites/fit/ folder. Scheduled runs review one topic in depth for accuracy, audience purity, and staleness. Interactive runs write or update pages following documentation standards. Use when writing, editing, auditing, or reviewing documentation, or running scheduled documentation review. |
| **kata-implement** | Implement a spec by studying its spec.md and plan, then executing the plan step by step. Use when a spec and plan are approved and ready for implementation. Triggers: "implement spec NNN", "implement the plan for spec NNN", "execute plan NNN", "build spec NNN", "start implementation of NNN". |
| **kata-metrics** | Time-series data recording and analysis protocol for Kata agents. Defines CSV schema, storage conventions, metric design guidance, and XmR control chart analysis via `fit-xmr`. Utility skill — no agent routes to it directly; entry-point skills reference it for recording and analysis. |
| **kata-plan** | Write implementation plans (HOW/WHEN) for approved designs. Translate an approved design into concrete steps, file changes, sequencing, and risks for a trusted agent to execute. Sets plan phase to draft in specs/STATUS. |
| **kata-product-evaluation** | Supervise a product evaluation session where an agent tries a product as a first-time external user. Guide the session, capture feedback, and create GitHub issues for actionable findings. |
| **kata-product-issue** | Triage open GitHub issues against the product vision. Classify each as trivial fix, product-aligned spec, or out-of-scope, and produce a report the agent acts on. Operates on issues only — PR mergeability is kata-product-pr. |
| **kata-product-pr** | Merge gate for open pull requests. Verify contributor trust, parse PR type, check CI status, review spec quality, and merge PRs that pass all gates. Operates on PRs only — issue triage is kata-product-issue. |
| **kata-release-readiness** | Check open pull requests for merge readiness. Rebase branches on main, fix trivial CI failures (lint, format, lock file), and report status. Do not make code-level decisions or approve PRs. |
| **kata-release-review** | Review the main branch for unreleased changes and cut new versions. Determine version bumps, update package.json files, tag releases, push tags, and verify publish workflows. Canonical source for the release procedure. |
| **kata-review** | Grade a single artifact (spec, design, plan, or implementation diff) against quality criteria and return findings by severity. Use when another skill spawns a fresh sub-agent for an independent review of its work. This skill never spawns sub-agents — it produces findings only — which structurally prevents the spec/design/plan/implement review loop from recursing. |
| **kata-security-audit** | Perform a holistic security review of the monorepo. Assess GitHub Actions supply chain, dependency hygiene, credential leak controls, CI audit gates, and application-level vulnerabilities. Use when reviewing PRs for security impact, auditing the repo posture, or investigating a reported vulnerability. |
| **kata-security-update** | Apply security updates to the repository. Triage open Dependabot PRs against repository policies, review npm audit findings, and action dependency vulnerabilities. Merge PRs that pass all checks, fix minor issues on a new branch, or close PRs that violate policy. |
| **kata-session** | Toyota Kata coaching protocol for facilitated sessions. Used by the improvement coach (facilitator) and by domain agents who participate via the Ask/Answer/Announce orchestration tools. Same five coaching kata questions across team storyboard meetings and 1-on-1 coaching sessions; mode-specific guidance lives in references/team-storyboard.md and references/one-on-one.md. |
| **kata-setup** | Set up the Kata Agent Team in your repository. Walks through GitHub App creation, secret configuration, agent selection, and generates workflow files. Use when setting up a new Kata installation or adding agents to an existing one. |
| **kata-ship** | Ship the current feature branch as-is: approve, rebase on main, run checks, open (or reuse) a PR, wait for checks, and squash-merge into main. Ships only the work already done — never creates new work to complete a phase. |
| **kata-spec** | Write specifications (WHAT/WHY) for features, changes, and improvements. Sets spec phase to draft in specs/STATUS. Use when proposing changes, capturing findings as actionable specs, or evaluating spec quality. Pair with the `kata-plan` skill for the HOW side. |
| **kata-trace** | Go and see the work agents did by analyzing their execution traces. Select a workflow run, download its trace artifact, observe every turn via grounded theory, and produce a structured findings report with instruction-layer attribution. |
| **kata-wiki-curate** | Curate the wiki (agent memory) for cross-team collaboration. Verify summary accuracy against weekly logs, follow up on stale teammate observations, update MEMORY.md, and clean log hygiene. Use when running scheduled wiki curation, auditing agent memory health, or checking cross-agent communication. |
