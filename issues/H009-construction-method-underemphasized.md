---
agreement: 0.67
category: exposition
id: H009
location:
  file: paper/writeup/optimize.tex
  lines:
  - 430
  - 432
models_flagged: []
severity: moderate
source_job: holistic
title: Construction method deserves more prominence in main text
type: logical
---

# Construction method deserves more prominence in main text

## Flagged text

> To the best of our knowledge, this method is novel. An application of the method is presented in Appendix.

## Problem

The construction method — parameterizing prompts with continuous traits and optimizing via Bayesian optimization — is claimed as novel but applied only in Appendix A. All main-text experiments use the selection method only. No guidance on when to prefer one method over the other.

## Evidence gathered

**Searched for:** Construction method discussion
**Locations checked:** Section 2.4, Appendix A

- Lines 430-432: Claimed as novel, relegated to appendix
- Section 2.4 (lines 445-458): Brief description only
- All empirical evidence in Appendix A

## Suggested fix

Add discussion of when to prefer selection vs. construction method, or move one construction-method result to the main text.

## Severity votes

| Model | Severity | Reasoning |
|-------|----------|-----------|
| claude-sonnet-4-6 | minor | ## Severity Rating: 2/5 (Minor) |
| gpt-4o | moderate | I would rate the severity of this issue as moderate. The construction method is claimed to be novel, yet it is not given enough prominence in the main text, which could undermine the perceived significance and impact of the research. By not providing guidance on when to prefer one method over the other, the paper may leave readers without a clear understanding of the practical implications and applications of the proposed methods. |
| gemini-2.5-pro | moderate | **Severity Rating:** High |

**Consensus: moderate** (1/3 minor, 2/3 moderate)

## Draft author response

**Recommended action**: acknowledge

**Response draft**:

We agree that the construction method could benefit from more discussion. We have added a sentence at the end of Section 2.4 noting when each method is preferable.

**Manuscript changes**:

- `writeup/optimize.tex` after line 458 (end of construction method paragraph): Add: "In general, the selection method is preferable when the researcher has a discrete set of qualitatively distinct candidate \persona{s} (e.g., different reasoning types), while the construction method is better suited when behavior can be parameterized along continuous dimensions (e.g., degrees of altruism or risk aversion). The construction method may also be more sample-efficient when the candidate space is high-dimensional, as Bayesian optimization can explore it more systematically than enumeration."
