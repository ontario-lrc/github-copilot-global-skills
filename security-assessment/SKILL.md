---
name: security-assessment
description: Perform scoped threat analysis and read-only assessment of software security controls and vulnerabilities.
---

# Security assessment

## Procedure
1. Confirm assessment scope, assets, data sensitivity, actors, environment, and exclusions.
2. Identify trust boundaries, attack surfaces, entry points, and plausible threat scenarios.
3. Select security domains relevant to the system: identity, access control, input handling, data protection, cryptography, APIs, dependencies, configuration, logging, infrastructure, and availability.
4. Inspect architecture, source, configuration, and dependency evidence.
5. Research current primary sources such as official standards, vendor advisories, and recognised security organisations.
6. Validate each finding against a plausible attack path or concrete weakness.
7. Assess impact, likelihood, severity, and confidence separately.
8. Recommend practical remediation and verification.
9. State what was not assessed and residual uncertainty.

Do not execute scanners, exploit code, or perform active penetration testing unless a separate authorised capability and explicit scope are provided. Never claim comprehensive security or compliance from a limited review.