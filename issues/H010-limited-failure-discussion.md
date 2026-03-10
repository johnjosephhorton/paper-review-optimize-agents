---
id: "H010"
title: "Limited discussion of when AI agents might systematically fail"
type: logical
location:
  file: "paper/writeup/optimize.tex"
  lines: [1386, 1423]
source_job: "holistic"
models_flagged: []
category: "scope-and-limitations"
---

# Limited discussion of when AI agents might systematically fail

## Flagged text

> Although this approach provides no statistical guarantees for arbitrary novel settings

## Problem

The conclusion is almost entirely positive, with failure mentioned only as a brief statistical caveat. No dedicated discussion of when the approach is expected to fail, what domains are poorly suited, or how practitioners should recognize when personas are not working.

## Evidence gathered

**Searched for:** Failure discussion, limitations section
**Locations checked:** Conclusion (Section 5), Section 2.3

- Line 1398: Brief caveat about no guarantees for arbitrary novel settings
- Lines 384-388: One sentence noting boundaries of theory are not always well-defined
- No dedicated limitations subsection
- No discussion of cultural context dependence, theory misspecification, or LLM training data biases

## Suggested fix

Add a limitations paragraph in the conclusion discussing: (1) domains where clean theories are absent, (2) settings where LLM training data may introduce systematic biases, (3) how to detect when the approach is failing.
