---
name: implementation-workflow
description: Guide scoped implementation, debugging, and refactoring work.
---

# Implementation workflow

## Procedure
1. Confirm approved scope, requirements, design, and permissions.
2. Inspect the affected code and existing conventions.
3. Identify the smallest coherent implementation plan.
4. Implement the change while preserving unrelated work and public contracts.
5. Add or update focused implementation-level tests.
6. Review changed code for correctness, error handling, edge cases, security, and unintended side effects.
7. Run only authorised, relevant checks.
8. Report changed files, behaviour, validation results, and limitations.

For defects, reproduce or isolate the failure when feasible before changing code. For refactoring, preserve observable behaviour unless a behaviour change is explicitly requested. Do not silently broaden scope.