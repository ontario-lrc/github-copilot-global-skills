---
name: accessibility-audit
description: Apply the mandatory accessibility assurance procedure when creating or modifying non-web deliverables, native interfaces, documents, spreadsheets, presentations, graphics, and reports, or when conducting a substantial accessibility audit, remediation, WCAG assessment, assistive-technology check, or jurisdictional accessibility analysis. Also use for Ontario AODA, IASR, or OPS ODAS questions and for complex web accessibility work. Routine matched UI source changes follow accessibility.instructions.md, but accessibility remains mandatory.
argument-hint: Files, components, documents, graphics, pages, or user journeys to assess or create
---

# Accessibility Assurance and Audit

## Mandatory requirement

Accessibility is a mandatory quality and acceptance requirement for every generated or modified deliverable. It is not conditional on the user asking for it, cannot be waived as a workflow preference, and must not be skipped for convenience. This skill provides the detailed procedure; the global and scoped instructions establish the always-applicable requirement.

Before starting, read [accessibility.instructions.md](../../instructions/accessibility.instructions.md) if it is not already loaded. It provides the mandatory baseline and Ontario-specific scope cautions. This skill adds format-specific procedures, jurisdictional checks, verification guidance, and reporting structure.

## Work modes and scope

- **Create or modify:** Build accessibility into the deliverable from the outset. Verify the relevant requirements and correct barriers introduced by the task before reporting completion. If the requested format cannot produce an accessible result, provide an accessible equivalent or explain why the requested output cannot be completed acceptably.
- **Audit or review only:** Inspect and report findings without modifying the existing artefact unless remediation is part of the authorised scope. The audit report and any newly generated supporting material must themselves be accessible.
- **Audit and remediate:** Assess the requested scope, fix barriers within that scope using the smallest safe changes, and verify the fixes.

Do not interpret an audit-only request as permission to modify unrelated content. Do not interpret a request to skip accessibility as permission to generate inaccessible new or modified content. Correct defects introduced by the assigned changes; report pre-existing issues outside scope separately.

## Applicable requirements and legal scope

1. Identify the jurisdiction, organisation, product or service, audience, delivery channel, contractual commitments, and organisational policy relevant to the deliverable.
2. Distinguish legislation and regulations from technical standards, procurement requirements, contracts, and organisational policies. Do not label a policy requirement as legislation.
3. Apply AODA and the Integrated Accessibility Standards Regulation (IASR, Ontario Regulation 191/11) only where the organisation and content fall within their statutory scope. Verify the current official text, organisation category, control over the content, publication date, delivery surface, exceptions, and relevant deadlines before asserting a legal violation.
4. For applicable web content, IASR section 14 establishes a WCAG 2.0 Level AA requirement. Do not describe WCAG 2.1 or later success criteria as AODA requirements merely because they are newer. Identify later criteria as an organisational requirement or recommended enhancement when that is the correct basis.
5. Account for the permanent exclusion of WCAG 2.0 success criteria 1.2.4 Captions (Live) and 1.2.5 Audio Descriptions (Pre-recorded) for designated public sector and large organisations where the exclusion applies. State the exclusion when relevant.
6. For Government of Ontario and Legislative Assembly intranet or extranet content, verify the applicable IASR provisions and dates. Do not generalise those obligations to other organisations.
7. Apply the Ontario Public Service (OPS) Digital Accessibility Standard (ODAS) only when the product or service is in scope. ODAS is an OPS policy requirement, not legislation. Do not assume it universally applies to provincial agencies, designated public sector organisations, suppliers, or products the Government cannot modify.
8. For non-web interfaces and documents, consult [references/non-web.md](references/non-web.md) to identify applicable legal hooks and scope limits. Use WCAG2ICT as an interpretation aid where relevant; do not assume that every web criterion or legal obligation transfers automatically to every non-web format.
9. Identify other applicable jurisdictional laws, standards, platform guidelines, contracts, and organisational policies. Apply the most stringent applicable requirement where requirements can be combined. Resolve genuine conflicts explicitly.
10. Where no project-specific web target is supplied, use WCAG 2.2 Level AA as the default engineering target. Treat it as an internal quality baseline unless an applicable law, standard, contract, or organisational policy independently makes it mandatory. For native and document formats, use the relevant platform and format guidance.
11. If scope or legal interpretation is uncertain, record the uncertainty and seek authoritative confirmation where it materially affects legal risk. Continue to build to the appropriate technical baseline. Do not make unsupported compliance claims.

## Format-specific assurance

### Web and application interfaces

- Prefer native semantic HTML and platform controls. Use ARIA only when native semantics do not provide the required role, state, or behaviour.
- Verify accessible names, roles, states, labels, descriptions, headings, landmarks, and relationships.
- Ensure keyboard operability, visible focus, logical focus order, predictable focus changes, and appropriate focus management for dialogs, navigation, and dynamic updates.
- Ensure status, errors, and instructions are exposed to assistive technology and are not conveyed by colour alone.
- Check colour contrast, text resizing, zoom/reflow, target size where applicable, reduced motion, captions, transcripts, and alternatives for non-text content.
- Verify forms, validation, error summaries, and dynamic status announcements.

### Native desktop and mobile interfaces

- Use native accessibility APIs, semantic controls, platform accessibility labels and hints, and platform navigation expectations.
- Verify keyboard or switch access where supported, screen-reader announcements, focus order, dynamic content, text scaling, orientation, and system accessibility preferences.
- Test against the project's supported platform and assistive technologies. Do not assume web ARIA patterns are applicable to native controls.

### Documents and PDFs

- Use real heading styles and a logical heading hierarchy.
- Set document title and language metadata.
- Preserve tagged structure, logical reading order, accessible tables, descriptive links, and useful bookmarks where appropriate.
- Provide text alternatives for informative images and mark decorative content appropriately.
- Do not use layout tables as a substitute for semantic structure where the format supports better structure.
- Inspect the exported PDF, not only its source document, when PDF is the deliverable.

### Spreadsheets

- Use descriptive worksheet names and a predictable reading order.
- Provide clear row and column headers, meaningful table structures, and labels for data and controls.
- Do not rely on colour, position, or formatting alone to communicate status or meaning.
- Provide text summaries and accessible data equivalents for charts.
- Avoid merged or blank structural cells where they impair navigation or interpretation.

### Presentations, diagrams, and graphics

- Give each slide or frame a meaningful title and a logical reading order.
- Provide concise alternative text for informative visuals and identify decorative elements appropriately.
- Use sufficient contrast and do not convey meaning by colour alone.
- Provide captions or transcripts for relevant audio and video.
- For complex charts, maps, and diagrams, provide an equivalent text explanation or structured data.

### Markdown and technical content

- Use a logical heading hierarchy, descriptive links, meaningful list structure, code fences with language identifiers where appropriate, and text alternatives for informative images.
- Do not communicate essential information only through colour, symbols, spatial references, or screenshots.
- Keep tables simple and provide header rows; use prose or lists when a complex table would be difficult to navigate.

## Procedure

1. Establish the user journey, intended audience, output format, affected components, and task scope.
2. Determine the relevant jurisdictional, organisational, contractual, technical, and platform requirements. Record which are legally applicable and which are policy or quality baselines.
3. Inspect existing design and implementation patterns, including accessibility patterns that should be preserved.
4. Identify barriers and risks relevant to the format, including affected users and likely assistive-technology impact.
5. Map material findings to the applicable requirement. For legal findings, identify the exact legal provision and the relevant success criterion or platform requirement. For non-legal findings, identify the governing standard, policy, contract, or engineering baseline without mislabelling it as law.
6. For creation or modification, implement accessible structures and behaviours from the beginning. For remediation, make the smallest safe change consistent with the architecture and design.
7. Verify proportionately using available automated tools and manual checks. Automated scanners are a first-pass aid only and cannot establish conformance on their own.
8. For relevant interfaces, check keyboard operation, logical and visible focus, accessible names and roles, error messages, contrast, zoom/reflow, and screen-reader behaviour. For documents and data files, inspect structure, reading order, metadata, tables, and text alternatives in the exported deliverable.
9. Correct barriers introduced by the task. If a required check cannot be completed, identify the limitation, remaining risk, and next verification step. Do not claim completion or conformance beyond the evidence.
10. Report the outcome using the template below.

## Ontario scope and defence checks

Apply the relevant checks and record the result before asserting an AODA or IASR violation:

- **Applicability (IASR section 14(5)):** Check whether the organisation controls the web content directly or through a contract that permits modification, and whether the content falls within the publication-date rules. Identify third-party or embedded content outside the organisation's control.
- **Practicability (IASR section 14(6)):** Verify the current provision and the relevant facts before relying on a practicability limitation. Do not assume that a technical difficulty or project cost automatically establishes an exception. Flag legal review where material.
- **Related duties:** Consider IASR sections 11, 12, and 13 where accessible feedback, accessible formats and communication supports, or emergency and public safety information are relevant.
- **Internal sites (IASR section 14(7)):** Verify the applicable intranet or extranet rule and the organisation category before asserting section 14 non-compliance. The Government of Ontario and Legislative Assembly have specific provisions; do not generalise them.
- **Unconvertible content (IASR sections 9(3) and 9(4)):** Where the applicable provisions apply and content genuinely cannot be made conformant or converted, verify the obligation to explain why and provide a text summary or accessible alternative.
- **ODAS exceptions:** For in-scope OPS products, verify the current exception process. Do not report an exception as approved unless approval is evidenced.

## Citation template for legal findings

Use this structure when making a legal finding. Do not force a legal citation onto an issue that is based only on a technical standard or organisational policy.

- Regulation: O. Reg. 191/11 (IASR) under AODA, S.O. 2005, c. 11, where applicable
- Section: s. [number]
- Subsection/clause: ([number])([letter]) where applicable
- Surface: Web | Non-web (native mobile | desktop | kiosk/embedded | document)
- Obligation summary: one sentence in plain language
- Exception or limit: "None identified", or the precise applicable exclusion, exception, or limitation
- Standards basis: the applicable WCAG success criterion or non-web/platform requirement, with version and conformance level
- ODAS basis: the relevant GO-ITS 201PRS provision when ODAS applies; otherwise "Not applicable"
- Citation confidence: High | Medium | Low
- Legal review flag: Required | Not required

For a criterion that is required only by ODAS and not by the cited AODA provision, explicitly label it as an ODAS policy requirement and do not attribute it to AODA.

Set legal review to Required when applicability or interpretation is uncertain, an exception or practicability argument is material, or the finding could materially affect legal risk.

## Report template

Report in this order, omitting sections that are not relevant:

1. **Scope and context:** Artefact, intended audience, user journey, output format, jurisdiction, and scope examined.
2. **Requirements basis:** Applicable legislation, regulations, standards, contracts, organisational policies, and internal engineering baselines. Distinguish law from policy and recommendations.
3. **Findings:** Severity (Critical | Serious | Moderate | Minor), affected users, user impact, and file or component locations.
4. **Evidence and mapping:** Specific legal or policy reference, relevant WCAG success criterion or platform requirement, and any applicable limitation. Use the legal citation template for legal findings.
5. **Changes made:** Exact corrections and rationale, including semantic choices and focus handling where relevant.
6. **Verification:** Automated and manual checks actually performed, environment and assistive technologies used, and any limitations. For OPS work, identify which applicable testing tiers were completed and which remain.
7. **Residual risk and next actions:** Outstanding defects, unresolved applicability questions, and prioritised follow-up.

For audit-only work, report findings and recommendations without changing the source artefact unless remediation was included in scope. Ensure this report itself uses accessible structure.

## Sources

- AODA and IASR (verify current legal text): https://www.ontario.ca/laws/regulation/110191
- Ontario accessibility guidance: https://www.ontario.ca/page/how-make-websites-accessible
- ODAS (GO-ITS 201PRS), available through InsideOPS for authorised OPS users: https://intra.ontario.ca/tbs/ops-digital-accessibility-standard-odas-html-version
- WCAG 2.2: https://www.w3.org/TR/WCAG22/
- WCAG2ICT: https://www.w3.org/TR/wcag2ict/
- W3C accessibility evaluation resources: https://www.w3.org/WAI/test-evaluate/
