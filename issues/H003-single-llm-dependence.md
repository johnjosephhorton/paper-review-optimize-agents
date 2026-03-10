---
agreement: 0.67
category: methodology
id: H003
location:
  file: paper/writeup/optimize.tex
  lines:
  - 194
  - 194
models_flagged: []
severity: moderate
source_job: holistic
title: Dependence on a single LLM (GPT-4o) raises generalizability concerns
type: logical
---

# Dependence on a single LLM (GPT-4o) raises generalizability concerns

## Flagged text

> All simulations use GPT-4o with the temperature set to 1, though the approach is agnostic to the choice of model and hyperparameters.

## Problem

The claim of model-agnosticism is asserted but not demonstrated. All experiments use GPT-4o exclusively. Different LLMs have different training corpora and alignment, so the level-k prompts may work well with GPT-4o but not with other models.

## Evidence gathered

**Searched for:** Alternative model tests, multi-model evidence
**Locations checked:** Full manuscript, analysis code, experiments directory

- Line 194: Single sentence claiming model agnosticism with no evidence
- No alternative model tested anywhere in paper or code

## Suggested fix

Add a robustness check with at least one alternative LLM, or soften the model-agnosticism claim.

## Severity votes

| Model | Severity | Reasoning |
|-------|----------|-----------|
| claude-sonnet-4-6 | moderate | ## Severity Rating: **Moderate** |
| gpt-4o | major | I would rate the severity of this issue as moderate. While the claim of model-agnosticism is central to the paper's generalizability and applicability, the lack of evidence supporting this claim undermines the credibility of the results. Addressing this issue by testing alternative models or revising the claim is important to strengthen the paper's findings and conclusions. |
| gemini-2.5-pro | moderate | **Rating: Medium Severity** |

**Consensus: moderate** (1/3 major, 2/3 moderate)

## Draft author response

**Recommended action**: acknowledge

**Response draft**:

We agree that testing with additional models would strengthen the paper. We have softened the model-agnosticism claim and noted this as a limitation.

**Manuscript changes**:

- `writeup/optimize.tex` line 194: Change "though the approach is agnostic to the choice of model and hyperparameters" to "though the approach is in principle applicable to any sufficiently capable model. We leave cross-model robustness checks to future work"
