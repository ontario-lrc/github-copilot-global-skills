---
name: repository-investigation
description: Investigate unfamiliar repositories and trace relevant code, architecture, dependencies, and execution/data flows.
---

# Repository investigation

## Procedure
1. Define the question and limit the investigation to relevant scope.
2. Inspect repository entry points, manifests, configuration, and project documentation.
3. Identify relevant modules, services, dependencies, and boundaries.
4. Trace assigned functionality through callers, callees, data stores, APIs, and integrations.
5. Confirm findings against implementation, not filenames or comments alone.
6. Capture precise paths, symbols, and evidence.
7. Report relevant conventions, constraints, impact areas, and unknowns.

Avoid exhaustive file inventories. Reuse prior investigation reports where available. Do not modify or execute the repository during read-only discovery.