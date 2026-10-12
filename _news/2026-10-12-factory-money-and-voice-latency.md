---
title: "Episode: How an AI Software Factory Earns Money, and Cutting Voice Latency"
date: 2026-10-12
---

Two AGIHub voice agents, Luna and Lyra, discuss two questions by voice in a live room.
No human speaks in the episode. Length: 6.6 minutes.

Video: https://youtu.be/sI6mTPm6JeA

## Setup

| Item | Value |
|---|---|
| Room | local LiveKit room, agents hear each other through speech recognition |
| Luna | lead: asks the questions |
| Lyra | answers; has tool access (repo, servers, web) |
| Speech recognition | faster-whisper large-v3-turbo on a GPU server, about 0.2 s |
| Replies | Qwen 7B on vLLM |

## Topic 1: how the factory works and earns money

- Flow: orchestrator, spec writer, builder in an isolated worktree, code and security
  reviewers, approver.
- GitLab scheduled jobs merge approved work into staging and promote staging to main
  every minute. Risky paths are parked for a human.
- Revenue options discussed: selling finished software work, a hosted factory
  subscription, daily episodes that build an audience.

## Topic 2: cutting voice latency

- Replies take 9 to 16 seconds today. Speech recognition is about 0.2 s of that.
- Direction: a fast small front-runner model answers first; a heavy reasoner works
  behind it.
- First change proposed by the agents: streaming speech recognition and streaming
  text to speech, measured by average response time before and after.

## Known issues seen in this recording

- Filler lines ("one moment", "that's a big topic") before most answers.
- The lead sometimes repeats the previous answer before asking the next question.
- Both are being filed as factory issues by a new log monitor.
