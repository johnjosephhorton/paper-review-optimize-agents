---
agreement: 0.67
category: methodology
id: H008
location:
  file: paper/writeup/optimize.tex
  lines:
  - 639
  - 645
models_flagged: []
severity: major
source_job: holistic
title: Chain-of-thought prompting may not be applied consistently across agent types
type: technical
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

## Severity votes

| Model | Severity | Reasoning |
|-------|----------|-----------|
| claude-sonnet-4-6 | moderate | ## Severity Rating: **3 – Moderate** |
| gpt-4o | major | I would rate the severity of this issue as moderate. The inconsistent application of Chain-of-Thought (CoT) prompting across different agent types can significantly impact the validity of the study's findings, as it introduces a potential confound that may skew performance comparisons. Addressing this issue is crucial to ensure that any observed differences in agent performance are genuinely due to theoretical grounding rather than the differential use of CoT prompting. |
| gemini-2.5-pro | major | **Severity Rating: 3/3 (Major issue)** |

**Consensus: major** (2/3 major, 1/3 moderate)
