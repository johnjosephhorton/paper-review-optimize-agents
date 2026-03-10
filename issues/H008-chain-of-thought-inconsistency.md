---
id: "H008"
title: "Chain-of-thought prompting may not be applied consistently across agent types"
type: technical
location:
  file: "paper/writeup/optimize.tex"
  lines: [639, 645]
source_job: "holistic"
models_flagged: []
category: "methodology"
---

# Chain-of-thought prompting may not be applied consistently across agent types

## Flagged text

> We then elicit each AI agent's responses using Chain-of-Thought prompting, which encourages step-by-step reasoning before producing a final answer.

## Problem

The paper uses a two-step CoT prompting procedure for the level-k agents, including reasoning explanations in the strategic persona prompts. It is unclear whether baseline and atheoretical agents receive the same treatment. If not, performance differences could partly reflect CoT benefits rather than theoretical grounding.

## Evidence gathered

**Searched for:** CoT prompting details, baseline prompting procedure
**Locations checked:** Section 3.3, Table 2 notes, footnote 23

- Footnote 23 (line 639): Two-step CoT procedure for strategic agents
- Table 2 note (line 645): Reasoning explanation included only for strategic personas
- No mention of CoT for baseline or atheoretical agents

## Suggested fix

Clarify whether CoT was applied to all agent types. If not, acknowledge this as a potential confound or provide a robustness check.
