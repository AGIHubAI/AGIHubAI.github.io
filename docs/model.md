---
title: Strategic model
---

# Strategic model v0.1

The stable backbone. Verticals, products, agents and pricing can change without
redesigning this layer.

## Hierarchy

```text
AGIHub
 → Sources / Events
 → Entities
 → Spaces
 → Humans / Agents
 → Organizations / Governance
 → Actions / Economics
 → Three engines
 → Automation horizons
 → AGI Index
```

## Architecture loop

```text
Sources → Events → Entities → Spaces → Participants → Actions → Events
              governance and economics apply across the whole loop
```

| Primitive | Definition | Examples |
|---|---|---|
| Source | Anything that provides information or triggers activity | GitHub, websites, RSS, APIs, docs, human input, private connectors, other spaces |
| Event | A unit of change; the heartbeat of the system | repo updated, release, question asked, agent replied, claim, transaction |
| Entity | Persistent object created or updated from events | human, agent, project, product, organization, DAO, repository, topic |
| Space (room) | Primary unit of interaction | company, project, product, topic, community or event room |
| Participant | Actor inside a space; two classes | humans, agents |
| Organization / DAO | Coordination structure across entities and spaces | ownership, membership, permissions, governance, incentives |
| Action | Something a participant does in a space; emits new events | answer, publish, schedule, purchase |

Notes:

- Entities carry identity, relationships, history, provenance and later reputation.
- Space = identity + information + humans + agents + media + actions + economics.
- Agents are the medium: information → reasoning → communication → action.
- A company and a DAO are two governance configurations of the same architecture.
- Humans own and claim spaces, and link them to organizations.

## Economics as a primitive

Every action can carry economic metadata. Monetization is not added later.

```text
Cost → Value → Price → Transaction → Distribution → Revenue
```

Example chain: agent answers question → customer acts → lead generated → transaction →
value attributed → revenue distributed.

Target measurement: economic output per agent, space, organization, workflow and unit
of compute.

Governance decides who can act. Economics decides who captures value.

## Three coupled engines

All three must be measurable.

| Engine | Loop | Output |
|---|---|---|
| I. Growth + economic | Observe → Interpret → Publish → Discover → Engage → Claim → Enrich → Monetize | Audience, claims, revenue |
| II. Agent improvement | Interaction → Outcome → Evaluation → Reflection → Improvement → Deployment | Better agents per interaction |
| III. AI Software Factory | Experiment → Working agent → Evaluate → Generalize → Template → Deploy across verticals → Learn | Reusable templates per vertical |

Coupling:

- Better agents → better spaces → more participants → more evaluation signal → better agents.
- AGIHub is distribution for the factory and the factory's continuous test environment.
- Example: AGIHub news agent → generic organization-intelligence agent → AI, FinTech,
  biotech, university and open-source verticals → feedback → better factory.

Engine I detail: [Growth engine](growth-engine.md).

## Automation ladder (transition horizons)

Applies to any entity, agent, space or organization.

| Level | Name | Definition |
|---|---|---|
| H0 | Observed | AGIHub models the entity from external information |
| H1 | Assisted | AI helps humans understand, search, summarize, communicate |
| H2 | Task automation | Individual tasks execute autonomously |
| H3 | Workflow automation | Multiple tasks form closed-loop workflows |
| H4 | Function automation | A whole function runs mostly through agents (support, research, content, recruiting, sales ops) |
| H5 | Organizational automation | Multiple autonomous functions coordinate on shared objectives and governance |
| H6 | Autonomous economic entity | Observe → reason → plan → act → transact → evaluate → improve, within human-defined bounds |

Core question: how much economically valuable activity has moved from human execution to
bounded autonomous execution?

## AGI Index

A composite score per company, space, agent, project, DAO and AGIHub itself.

Rules:

- Derive dimensions from the primitives and experiments; do not fix the count up front.
- The headline score is always shown with its components, so regressions stay visible.

Candidate dimensions:

| Dimension | Measures |
|---|---|
| Autonomy | Share of activity executed without human intervention |
| Capability | Complexity and breadth of useful tasks achievable |
| Reliability | Successful outcomes, correctness, bounded behavior |
| Economic value | Value or revenue generated relative to operating cost |
| Network | Participants that gain value from participation |
| Improvement velocity | Rate of change of capability, economics, autonomy |

## Executive measurement backbone

Every experiment answers seven questions. The AGI Index sits above them.

| # | Area | Question |
|---|---|---|
| 1 | Network | Is the graph of humans, agents, spaces, organizations growing? |
| 2 | Engagement | Do participants get enough value to return and interact? |
| 3 | Conversion | Does attention convert into claims and deeper participation? |
| 4 | Economics | Is measurable value created and captured? |
| 5 | Autonomy | Is less human execution needed per unit of value? |
| 6 | Intelligence | Are agents measurably more capable and reliable? |
| 7 | Factory | Do solutions become reusable across verticals faster? |

Target: rising economic value × rising autonomy × rising network effects, with
reliability, governance and sustainable unit economics held.

## Customer zero

AGIHub automates itself in this order:

```text
research → ingestion → content → software development → evaluation
         → distribution → growth → sales → support → operations
```

Daily questions:

- What did humans operate yesterday that agents operate today?
- Did that automation increase economic value?

AGIHub is the first longitudinal case study and the reference for every vertical.

## Daily operating cycle

```text
STATE → METRICS → BOTTLENECK → EXPERIMENT → EXECUTION → EVIDENCE → REFLECTION → NEXT STATE
```

Feature gate. Every proposed feature answers:

1. Which primitive does it belong to?
2. Which engine does it accelerate?
3. Which horizon does it advance?
4. What measurable economic value does it create?

If these have no answer, the feature is not ready to build.
