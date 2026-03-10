---
id: "H001"
title: "Theory-grounding requirement may be more restrictive than acknowledged"
type: logical
location:
  file: "paper/writeup/optimize.tex"
  lines: [384, 388]
source_job: "holistic"
models_flagged: []
category: "scope-and-limitations"
related_issues: ["H010"]
---

# Theory-grounding requirement may be more restrictive than acknowledged

## Flagged text

> The boundaries of a theory and the settings it plausibly governs are not always well-defined.

## Problem

The paper's evidence comes exclusively from settings with well-established, clean theoretical models (level-k for strategic games, social preferences for allocation games). Many applied prediction problems lack such clean theoretical structures. The paper acknowledges the challenge perfunctorily (one paragraph in Section 2.3) but never discusses the case where no well-specified theory exists, or where theories are vague or contested.

## Evidence gathered

**Searched for:** Discussion of limitations, failure cases, theory absence
**Locations checked:** Sections 2.3, 5 (conclusion)

- Lines 384-388: Brief acknowledgment that "boundaries of a theory...are not always well-defined"
- Conclusion (lines 1386-1423): Almost entirely positive; no dedicated discussion of settings where the approach would break down
- No discussion of domains where clean theories are unavailable

## Suggested fix

Add a paragraph in the conclusion discussing the approach's limitations when well-specified theories are unavailable.
