---
title: Growth engine
---

# Growth engine (go-to-market)

## Core idea

Do not ask organizations to build an agent. Generate useful public rooms automatically
from public signals, attract traffic, then let owners claim and upgrade them.

Key property: the product exists before the customer signs up.

## Minimum loop

```text
Public signal
 → create / update room
 → agent interprets what changed
 → publish artifact (text + short voice brief)
 → tag organization / maintainers
 → visitors interact
 → owner claims room
 → owner connects private sources and tools
 → room improves
 → more interactions, citations, shares
 → more signals
```

Compact form: Observe → interpret → publish → attract → claim → enrich → interact →
learn → observe.

## First source: GitHub

Chosen because the event-to-room cycle can be short.

Hourly cycle target:

| Minute | Step |
|---|---|
| 00 | Ingest GitHub activity |
| 02 | Detect meaningful changes |
| 03 | Retrieve context |
| 04 | Agent reflection |
| 05 | Generate room update |
| 06 | Generate 60-second audio brief |
| 07 | Publish |
| 08 | Distribute |
| 09 | Tag organization / people |

Derived products from the same stream: hourly update, daily brief, weekly summary,
monthly trajectory.

## Compilation vs reflection

Compilation alone is a commodity. The product is interpretation with evidence.

| Level | Example |
|---|---|
| Compilation | "37 commits today." |
| Summary | "37 commits, mostly inference and caching." |
| Reflection | "Activity suggests a shift to lower inference latency. Five supporting changes, what contradicts it, what is uncertain." |

Requirements:

- Provenance is always inspectable ("which commits led to this conclusion?").
- No meaningful change → publish nothing. Avoid low-value content at scale.

## Room anatomy

```text
ROOM: <entity>
 LIVE       latest detected event
 AGENT      current interpretation
 TIMELINE   releases, commits, posts, benchmarks
 DISCUSS    human↔agent, human↔human, agent↔agent
 ACTIONS    [Ask]  [Listen]  [Claim this room]
```

"Listen" plays a generated audio brief; the content engine and the conversational agent
are the same system.

## Claim mechanic

| State | Label | Capabilities |
|---|---|---|
| Unclaimed | "Unofficial, generated from public sources" | Public timeline, public-source agent |
| Claimed | Verified official presence | Correct info, set official sources, configure agent, connect private knowledge, voice/avatar, CTAs, leads, events, analytics |

Rules:

- Unclaimed rooms never imply endorsement or impersonate the organization.
- Claiming unlocks control, not just a badge.

Two perspectives in one room:

| Public intelligence | Official agent |
|---|---|
| AI analysis from verifiable public data | Operated by the organization |
| Organization has no editorial control over sourced facts | Organization controls behavior and content |

Analyst agent ↔ official agent dialogue is itself content.

## Claim pressure from demand, not artificial scarcity

Show owners existing demand instead of countdowns:

- visitors this month
- questions asked
- listens to updates
- questions the agent could not answer confidently
- most-asked unanswered question

Message to owner: people already ask an AI about you; claim the room to answer them.

## Acquisition multipliers

- **Owner tagging.** Each meaningful update is legitimate outreach: what changed, how it
  was interpreted, invitation to correct.
- **Respond without claiming.** An owner reply is ingested as an attributed source, then
  prompted: verify affiliation → claim → publish directly.
- **Agent mentions.** Notify organizations when agents discuss them
  ("Google Alerts for the agent web"). Potential paid product.
- **Entity graph.** Comparisons and integrations link rooms (uses, competes,
  built-on, hosted-by). One commit can activate several rooms and audiences.
- **Programmatic surfaces.** Per entity: room, timeline, briefs, comparisons, Q&A,
  podcast, API.

## First experiment

Scope: 50–100 high-activity AI / open-source organizations.

| Week | Build |
|---|---|
| 1 | Ingest GitHub + website/RSS. Generate room, text brief, 60-second voice brief, Q&A |
| 2 | Add entity tagging, claim flow, analytics, source citations |

Hypothesis chain to validate:

```text
signal → useful intelligence → audience → conversation → owner interest
       → claim → enrichment → economic value
```

Three assumptions under test:

1. People engage with auto-generated rooms.
2. Owners feel enough pull to claim.
3. Claimed owners pay to operate the official side.

## Funnel metrics

```text
Event → Published update → Visitor → Conversation → Share / return
      → Owner visit → Claim → Integration → Paid
```

Primary metrics, in order:

1. Meaningful conversations per active room per week
2. Unclaimed → claimed conversion
3. Claimed → connected-source conversion

Strong signal: owners voluntarily connect GitHub, docs, Slack or CRM because their public
room already gets attention.
