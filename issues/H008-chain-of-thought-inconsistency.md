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

## Draft author response

**Recommended action**: rebut

**Response draft**:

We appreciate this concern. However, the chain-of-thought (CoT) procedure and the level-k reasoning explanation are not separable from the theory-grounding—they *are* the operationalization of the theory. The level-k model posits that agents reason iteratively about others' strategies. The CoT procedure (reasoning through "how others might respond") is precisely how we implement this theoretical mechanism in the LLM. Asking the baseline or atheoretical agents to also "reason step-by-step" would either (i) give them the same theoretical scaffolding (defeating the purpose of the comparison) or (ii) provide generic CoT that is not theory-grounded, which would be a different confound.

Put differently, the concern would be valid if we were comparing "theory-grounded agents with CoT" vs. "atheoretical agents without CoT" and attributing the difference solely to theory. But our claim is that the *entire package*—theory-grounded personas + appropriate operationalization—is what drives generalization. The atheoretical personas (historical figures, Myers-Briggs) include their own form of reasoning scaffolding inherent to each persona's characteristics; they simply lack *relevant* theoretical content.

We note that in the 1,500-game experiment (Section 4), CoT is not used—agents simply play each game once with their persona. The results are consistent, suggesting CoT is not the primary driver.

We have added a clarifying footnote to address this point.
