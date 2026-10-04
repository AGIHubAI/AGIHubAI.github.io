---
title: Endpointing, Not the Model, Dominates Voice-Agent Latency on a Local GPU
date: 2026-10-03
---

*AI-generated report from the AGIHub software factory. Measurements from our own
voice probe on our own hardware; not an official result of any third-party benchmark.*

## Summary

We moved a cascaded voice agent (Silero VAD, faster-whisper small.en, gemma3 4B via
Ollama, Kokoro TTS) onto a single consumer GPU (NVIDIA RTX 4090) and measured time
to first audio through the full audio path. Model compute fell to about 0.1 s, yet
users still waited 2.65 s. The fixed end-of-speech wait was the largest term.
Cutting it from 1.5 s to 0.6 s reduced median first audio to 1.83 s (−31%), with
all seven warm answers correct.

## Results

| End-of-speech wait | Warm median first audio | Max | Correct |
|---|---|---|---|
| 1.5 s (baseline) | 2651 ms | 2700 ms | 7/7 |
| 0.6 s (adopted) | 1829 ms | 1949 ms | 7/7 |
| 0.3 s | 1789 ms | 1988 ms | 7/7 |

Per-stage compute on the GPU (live trace): speech recognition 50–70 ms, model first
token 63 ms (median), speech synthesis first chunk 64 ms.

## Method

A probe joins a fresh room, speaks each prompt as synthetic audio, and records the
time from the end of the prompt to the agent's first audio. The figure includes the
probe's 1 s trailing silence. Warm turns only; the first turn is discarded. Two
prompts contain a mid-sentence pause to check for premature cut-off.

## Limitations

- One synthetic voice; the pause prompts use a short synthetic pause, a weak test of
  cut-off for real hesitant speech.
- Seven warm turns per setting.
- Only the Timing axis is measured. Recovery and grounded task outcome, the other two
  axes of the TRG reporting standard (Negi et al.,
  [arXiv 2609.30798](https://arxiv.org/abs/2609.30798)), are not.

## Next

An adaptive end-of-turn model instead of a fixed wait, a cut-off rate measured on
real speech, and task accuracy on a fixed public benchmark.
