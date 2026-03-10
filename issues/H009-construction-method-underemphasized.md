---
id: "H009"
title: "Construction method deserves more prominence in main text"
type: logical
location:
  file: "paper/writeup/optimize.tex"
  lines: [430, 432]
source_job: "holistic"
models_flagged: []
category: "exposition"
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
