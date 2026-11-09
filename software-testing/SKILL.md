---
name: software-testing
description: Design and execute risk-based software tests and independent quality assurance.
---

# Software testing

## Procedure
1. Confirm requirements, expected behaviour, scope, environment, and test permissions.
2. Review existing test structure and avoid duplicating adequate coverage.
3. Prioritise risk and define positive, negative, boundary, exception, integration, and regression scenarios as appropriate.
4. Define test data, setup, expected outcomes, and cleanup.
5. Create or update test artefacts using project conventions.
6. Execute only authorised tests in an appropriate environment.
7. Record exact results and distinguish product defects from test/environment failures.
8. Map outcomes to acceptance criteria where possible.
9. Independently verify fixes when assigned.

Never weaken tests to force a pass. Do not modify production code to fix defects. Confirm safety before tests that mutate data, contact external services, incur cost, or affect real users.