---
name: accessibility-audit
description: 'Use this skill when the user asks for an accessibility audit, review, or fix, or asks about Ontario accessibility law: checking Accessibility for Ontarians with Disabilities Act (AODA) or Integrated Accessibility Standards Regulation (IASR, Ontario Regulation 191/11) compliance, checking an Ontario ministry product against the Ontario Public Service (OPS) Digital Accessibility Standard (ODAS), running Web Content Accessibility Guidelines (WCAG) or assistive-technology checks, or fixing Accessible Rich Internet Applications (ARIA), keyboard, focus, colour contrast, screen reader, form, or dialog defects. Use it even when the user does not say "accessibility", such as when something cannot be reached by keyboard, is not announced by a screen reader, or is hard to see. Covers any web framework, such as React, Angular, Vue, Svelte, or Web Components, plain markup, styles, and scripts, and non-web user interfaces, such as native mobile, desktop, and kiosk software and documents. Routine user-interface changes do not need it, because accessibility.instructions.md covers them.'
argument-hint: 'Files, a component, a page, or a user journey to audit'
---

# Accessibility Audit

Audit user interfaces and content for accessibility barriers under the Accessibility for Ontarians with Disabilities Act (AODA) and, for Ontario ministry work, the Ontario Public Service (OPS) Digital Accessibility Standard (ODAS), fix each barrier with the smallest verifiable change, and report every finding with a legal or ODAS citation.

Before starting, read [accessibility.instructions.md](../../instructions/accessibility.instructions.md) if it is not already loaded. It holds the legal baseline, the ODAS rules, and the coding rules that every fix must follow; this skill adds the audit procedure, the legal scope checks, and the report templates. Treat the legal rules in both files as legal requirements, which rank first in the global precedence order, and the ODAS rules as mandatory policy, not law.

## Rules

- Propose and apply only changes that are traceable to AODA or Integrated Accessibility Standards Regulation (IASR) requirements, or to ODAS requirements for work in its scope, supported by Web Content Accessibility Guidelines (WCAG) success criteria and by native-semantics best practices. Apply the success criteria directly for the web, or as interpreted by the World Wide Web Consortium (W3C) guidance on applying WCAG to non-web information and communications technologies (WCAG2ICT) for non-web user interfaces.
- Cite the specific legal reference for every finding, or the ODAS reference when only ODAS imposes the requirement, in the format that "Citation Template" defines, including any exception, exclusion, or practicability limit that applies.

## Procedure

1. Identify the affected user journey and the specific barrier, and name the affected disability groups, such as blind and screen reader users, low vision, motor and keyboard-only, cognitive, and deaf and hard of hearing.
2. Confirm the supported browsers and assistive technology from the project or the user's messages, such as the screen readers NonVisual Desktop Access (NVDA) and Job Access With Speech (JAWS) on Windows and VoiceOver on macOS and iOS. Ask the user when neither settles it.
3. Determine the surface, web or non-web. For the web, the legal hook is IASR section 14. For a non-web surface, such as native mobile, desktop, or kiosk software or a document, read [references/non-web.md](references/non-web.md) to select the legal hook and the non-web scope checks, with WCAG2ICT as the interpretation method.
4. Apply "Scope and Defences", and record the result before asserting a violation.
5. Map each issue first to the AODA or IASR obligation, with exact section and subsection citations, then to the governing WCAG 2.0 success criterion, then, in ODAS scope, to the WCAG 2.1 success criterion that ODAS requires, and then to any recommended enhancement from the latest WCAG versions. Map an issue that only a WCAG 2.1 success criterion covers to ODAS alone.
6. Fix each issue with the smallest safe change that follows `accessibility.instructions.md`.
7. Verify each fix for keyboard-only operation and screen reader output, and confirm programmatic labels, error identification and instructions for forms, status that does not rely on colour alone, and contrast. Treat automated checkers, such as axe, axe DevTools, Lighthouse, and pa11y, as a first pass only, because they catch only about 30 to 40 percent of issues. Follow them with manual checks: keyboard-only operation, logical focus order, visible focus, and a screen reader walkthrough.
8. Report the results with "Report Template", including what was fixed, what remains, the residual legal risk, and the manual or assistive-technology testing still required. WCAG conformance requires human evaluation; for audits, reference the W3C Website Accessibility Conformance Evaluation Methodology (WCAG-EM). In ODAS scope, also state which of its three testing tiers, automated, manual, and assistive-technology testing, were completed, and whether the work triggers the ODAS accessibility report, which this audit does not replace.

## Additional Legal Rules

- Do not raise pure parsing or duplicate-identifier findings as conformance failures, because success criterion 4.1.1 Parsing is obsolete in WCAG 2.2 and deprecated by errata. Raise them only when they cause a real name, role, value, or assistive-technology defect.

## Scope and Defences

Apply these checks, and record the result, before asserting a violation.

- **Applicability (IASR section 14(5)):** The obligation covers web content that the organization controls directly or through a contract that allows modification, and content published after January 1, 2012. Flag a barrier that sits in third-party or embedded content outside the organization's control.
- **Practicability (IASR section 14(6)):** Conformance is not required where it is "not practicable". Relevant factors include the availability of commercial software or tools and a significant impact on an implementation timeline planned before 2012. If a fix is genuinely impractical, say so, set the legal review flag, and propose the closest accessible alternative instead of claiming hard non-compliance.
- **Related duties:** When relevant, consider IASR section 11 (accessible feedback process), section 12 (accessible formats and communication supports on request), and section 13 (accessible emergency and public safety information).
- **Internal sites (IASR section 14(7)):** Intranet and extranet sites are generally exempt from the section 14 WCAG 2.0 Level AA obligation, except that the Government of Ontario and the Legislative Assembly must meet it for their intranets. The section 12 duty to provide accessible formats on request still applies. Except for the Government of Ontario and the Legislative Assembly, do not assert a section 14 violation against an internal-only tool without confirming that it is a public internet site.
- **Unconvertible content (IASR sections 9(3) and 9(4)):** Where content genuinely cannot be made conformant or converted, such as some complex maps or diagrams, the duty is to explain why it is unconvertible and to provide a text summary or accessible alternative. Recommend that explanation and summary instead of reporting silent non-compliance.
- **ODAS exceptions:** In ODAS scope, every exception, including one based on practicability, must be submitted and approved through the OPS process for a Web Accessibility Compliance Exception. Until one is approved, report the requirement as unmet.

## Citation Template

For every finding, provide legal citations in exactly this structure. The template uses the standard abbreviations O. Reg. (Ontario Regulation), S.O. (Statutes of Ontario), c. (chapter), s. (section), SC (success criterion), and GO-ITS (Government of Ontario Information Technology Standard).

- Regulation: O. Reg. 191/11 (IASR) under AODA, S.O. 2005, c.11
- Section: s.[number]
- Subsection/Clause: ([number])([letter]) where applicable
- Surface: Web | Non-web (native mobile | desktop | kiosk/embedded | document)
- Obligation summary: one sentence in plain language
- Exception or limit: "None identified", or the exact exclusion or exception text and an applicability note, such as the permanent exclusion of SC 1.2.4 and 1.2.5, the s.14(6) practicability test, the s.14(7) intranet exemption, or s.9(4) unconvertible content
- Standards basis: for the web, WCAG 2.0 [SC number] - [title] at Level [A|AA], as required directly by IASR s.14; for non-web, WCAG 2.0 [SC number] - [title] at Level [A|AA], as interpreted by WCAG2ICT under the applicable AODA hook (s.6, s.12, Customer Service Part IV.2, or the Human Rights Code). Add "Recommended: WCAG [version] [SC number]" only as a clearly labelled enhancement from the latest WCAG versions.
- ODAS basis: in ODAS scope, GO-ITS 201PRS ODAS s.3.1, item 1: WCAG 2.1 [SC number] - [title] at Level [A|AA]; otherwise "Not applicable"
- Citation confidence: High | Medium | Low
- Legal review flag: Required | Not required

In ODAS scope, for a success criterion that WCAG 2.0 lacks, write "Not applicable (ODAS requirement only)" in the Regulation, Section, and Subsection/Clause fields.

Example (web):

- Regulation: O. Reg. 191/11 (IASR) under AODA, S.O. 2005, c.11
- Section: s.14
- Subsection/Clause: (4)
- Surface: Web
- Obligation summary: Designated public sector organizations and large organizations must make internet websites and web content conform to WCAG 2.0 Level AA.
- Exception or limit: Permanent exclusion of SC 1.2.4 Captions (Live) and SC 1.2.5 Audio Descriptions (Pre-recorded); the s.14(6) practicability test may apply.
- Standards basis: WCAG 2.0 SC 1.3.1 - Info and Relationships at Level A, required directly by IASR s.14. Recommended: WCAG 2.2 SC 2.5.8 Target Size (Minimum) as an enhancement.
- Citation confidence: High
- Legal review flag: Not required

Confidence guidance:

- High: The clause is explicit and directly applicable to the assessed scenario.
- Medium: The clause appears applicable, but its interpretation depends on context or implementation detail.
- Low: The clause mapping is uncertain, novel, or potentially contested.

Legal review guidance:

- Set "Required" when confidence is Medium or Low, when an exception, an exclusion, or the practicability defence may apply, when a conflict-of-laws (AODA section 38) or Human Rights Code interaction is in play, or when the compliance interpretation could affect legal risk.
- Set "Not required" only when confidence is High and no plausible exception or interpretive ambiguity is present.

## Report Template

Report in this order:

1. Findings: severity (Critical | Serious | Moderate | Minor), affected disability groups, user impact, and file locations.
2. Legal citations: the applicable AODA or IASR clauses, with section and subsection numbers, plus any relevant exclusion, exception, or practicability text.
3. AODA and ODAS mapping: the applicable AODA or IASR obligation, the governing WCAG 2.0 success criterion, in ODAS scope the WCAG 2.1 success criterion that ODAS requires, and any clearly labelled recommended enhancement from the latest WCAG versions.
4. Changes made: the exact fixes and their rationale, noting where native semantics were chosen over custom roles and any focus-management handling.
5. Verification notes: what was validated, such as keyboard operation, screen reader output, contrast, and programmatic labels, and what still needs manual or assistive-technology testing, including, in ODAS scope, which of its three testing tiers remain.
6. Next actions: a short checklist, prioritized by severity.

For each item in sections 1 to 3, follow "Citation Template" exactly. When "Legal review flag" is "Required", include a one-sentence reason.

## Sources

- AODA and IASR (the legal standard): https://www.ontario.ca/laws/regulation/110191
- ODAS (GO-ITS 201PRS), on InsideOPS behind an OPS sign-in, so ask the user to confirm its text: https://intra.ontario.ca/tbs/ops-digital-accessibility-standard-odas-html-version
- WCAG 2.0: https://www.w3.org/TR/WCAG20/
- Latest WCAG versions (best practice, and WCAG 2.1 for ODAS): https://www.w3.org/WAI/standards-guidelines/wcag/ (the W3C overview of every version), https://www.w3.org/TR/WCAG21/, and https://www.w3.org/TR/WCAG22/
- HyperText Markup Language (HTML), Cascading Style Sheets (CSS), and Accessible Rich Internet Applications (ARIA) specifications
