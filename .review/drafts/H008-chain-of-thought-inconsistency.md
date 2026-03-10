---
id: "H008"
title: "Chain-of-thought prompting may not be applied consistently across agent types"
type: technical
location:
  file: "writeup/optimize.tex"
  lines: []
source_job: "holistic"
models_flagged: []
---

# Chain-of-thought prompting may not be applied consistently across agent types

## Flagged text

> We then elicit each AI agent's responses using Chain-of-Thought prompting, which encourages step-by-step reasoning before producing a final answer.

## Problem

The paper uses chain-of-thought (CoT) prompting for the level-k agents (footnote 23) with a two-step procedure, but it is unclear whether baseline agents and atheoretical agents also receive CoT prompting. If not, the performance difference could partly reflect the benefit of CoT rather than the theory-grounding of the personas.
