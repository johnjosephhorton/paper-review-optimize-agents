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
