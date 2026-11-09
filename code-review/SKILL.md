---
name: code-review
description: Conduct evidence-based, read-only review of a software change set.
---

# Code review

## Review procedure
1. Establish the intended change and inspect the actual diff.
2. Read relevant requirements, design decisions, and adjacent implementation.
3. Trace changed logic and interfaces where needed.
4. Look for material correctness defects, broken invariants, edge cases, data integrity risks, error-handling gaps, compatibility problems, and maintainability concerns.
5. Inspect changed tests for meaningful assertions and coverage gaps.
6. Flag apparent security weaknesses, but refer dedicated threat/vulnerability analysis to the security-assessment skill/Agent 32.
7. Validate each candidate finding against evidence, impact, and conditions.
8. Remove duplicates, speculative concerns, and subjective style preferences.
9. Report actionable findings with location, severity, confidence, impact, and correction.

Do not edit files or execute code/tests. State review limitations and that tests were not run.