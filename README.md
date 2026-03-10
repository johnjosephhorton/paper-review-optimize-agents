# Paper Review: General Social Agents

**Authors**: Benjamin S. Manning & John J. Horton (MIT)
**Paper repo**: `/Users/johnhorton/topics/optimize_agents`
**Reviewed commit**: `863eccf`
**Reviewed at**: 2026-03-10
**Models**: claude-sonnet-4-6, gpt-4o, gemini-2.5-pro

## Summary

| Severity | Count |
|----------|-------|
| Major    | 3     |
| Moderate | 5     |
| Minor    | 0     |
| **Total** | **8** |

## Major Issues

- [H006: Small number of human observations per game (~3) limits game-level inference](issues/H006-small-human-sample-per-game.md)
- [H008: Chain-of-thought prompting may not be applied consistently across agent types](issues/H008-chain-of-thought-inconsistency.md)
- [H010: Limited discussion of when AI agents might systematically fail](issues/H010-limited-failure-discussion.md)

## Moderate Issues

- [004: Unexplained unanimous decision in setting 8](issues/004-unexplained-unanimous-decision-in-setting-8.md)
- [011: Bootstrap implementation details not reported](issues/011-potential-issues-with-bootstrapping-methodology.md)
- [H001: Theory-grounding requirement may be more restrictive than acknowledged](issues/H001-theory-grounding-restrictiveness.md)
- [H003: Dependence on a single LLM (GPT-4o) raises generalizability concerns](issues/H003-single-llm-dependence.md)
- [H009: Construction method deserves more prominence in main text](issues/H009-construction-method-underemphasized.md)

## Pipeline metadata

- Candidate issues found (broad sweep): 17
- Candidate issues found (holistic review): 10
- Total candidates: 27
- Confirmed after investigation: 8
- After deduplication: 8
- After severity voting: 8 (0 rejected as not_an_issue)
- Rejected as false positives: 19
