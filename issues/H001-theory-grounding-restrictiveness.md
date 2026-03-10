---
agreement: 1.0
category: scope-and-limitations
id: H001
location:
  file: paper/writeup/optimize.tex
  lines:
  - 384
  - 388
models_flagged: []
related_issues:
- H010
severity: moderate
source_job: holistic
title: Theory-grounding requirement may be more restrictive than acknowledged
type: logical
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

## Severity votes

| Model | Severity | Reasoning |
|-------|----------|-----------|
| claude-sonnet-4-6 | moderate | ## Severity Rating: **3/5 (Moderate)** |
| gpt-4o | moderate | I would rate the severity of this issue as moderate. While the paper acknowledges the challenge of applying its approach in settings without well-defined theoretical models, it does so only superficially and fails to explore the implications or provide guidance for such scenarios. This omission could limit the paper's applicability and relevance to a broader range of real-world problems where clean theoretical structures are not always present. Adding a discussion on these limitations would enhance the paper's robustness and utility. |
| gemini-2.5-pro | moderate | **Severity: 4/5 (Major Issue)** |

**Consensus: moderate** (3/3 moderate)
