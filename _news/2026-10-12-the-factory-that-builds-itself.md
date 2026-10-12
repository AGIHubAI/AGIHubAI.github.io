---
title: The AI Factory That Builds Itself
date: 2026-10-12
---

AGIHub is built by an AI software factory. The factory's own code lives in the
same repository it works on, so most changes to the factory are made by the
factory. A human operator sets direction, gates the control core, and decides
what gets published.

## The flow

Every unit of work is a GitHub issue. A stage label marks where it is.

| Stage | Who | Exit condition |
|---|---|---|
| Icebox | research agents | finding filed with sources and why it matters |
| Backlog | operator + lead session | prioritized |
| Spec | lead session | issue states scope, rules, falsifier |
| Build | builder agent | branch in an isolated worktree, tests pass, PR open |
| Review | code reviewer + security reviewer | findings written; reviewers never edit |
| Approve | approver agent | verdict recorded against the reviewed commit |
| Staging | merge workflow | approved PR merged to the staging branch |
| CI | automation | unit tests green on the staging commit |
| Main | automation or operator | staging fast-forwards to main; control-core changes wait for an operator merge |

Rules the factory enforces on itself:

- No agent session merges. An approved PR gets a ready label; a workflow merges
  it into staging.
- A second check re-reads the findings, the verdict, CI and mergeability
  independently of the approver. Any doubt is an escalation, never a merge.
- Changes to the control core (the review policy, the merge path, the agents'
  own permissions) never reach main without an operator merge.
- An escalation stops the loop. The fix goes into the factory (agents,
  checklists, skills), not only into the PR.

## Live numbers

Snapshot from the build repository, taken 2026-10-12 (UTC), GitHub REST API.

| Measure | Value |
|---|---|
| Pull requests merged, all time | 103 |
| Pull requests merged, last 7 days | 51 |
| Factory-built PRs since the loop went live (2026-10-11) | 23 |
| Factory PRs merged | 14 |
| Factory PRs escalated to the operator | 7 (30%) |
| Repeat escalations of the same class | 0 |

Escalation classes so far: CI, permissions, deploy, control core, unclassified.
A weekly job will publish these measures; until then this table is a manual
snapshot.

## The voice room

The operator runs the factory by voice from a live room. Agents in the room have
roles:

- **Luna**, project manager: talks with the operator, tracks status, posts tasks.
- **Tool worker**: quick read-only lookups across the codebase.
- **Claude**, tech lead: plans, reviews, and dispatches builders.
- **Builders, reviewers, approver**: run as separate sessions, one job each.

Spoken replies stay short. Detail goes to the screen and to the issue.

## Research team and the icebox

A research team of agents reads new papers and watches other software factories
(public repositories, changelogs, posts). Each finding becomes an icebox issue
with source links and one paragraph on why it matters. A room discussion
reviews the icebox; the lead session moves the useful items to the backlog.
This part is a spike: it passes if at least 3 of 10 filed items are worth
building.

## What is not automated

- Promotion to main of any batch that touches the control core.
- Publishing, including this page.
