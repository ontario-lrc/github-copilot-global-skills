# Non-Web User Interfaces and Documents

Use this reference for native mobile, desktop, kiosk, embedded software, and document deliverables. Establish the applicable jurisdiction and organisational scope before making a legal finding. Accessibility remains a mandatory engineering requirement even when a particular statutory provision does not apply.

## Legal hooks

- Do not apply IASR section 14 directly to native mobile, desktop, or kiosk software solely because it is a digital product. Section 14 addresses internet websites and web content, including web-based applications. Determine whether a document is legally treated as web content in its publication context rather than assuming that every document is covered by section 14.
- IASR section 6 may apply to obligated organisations when designing, procuring, or acquiring self-service kiosks. Verify that the device meets the statutory definition and that the organisation is within scope.
- IASR section 12 may require obligated organisations to provide accessible formats and communication supports upon request, subject to its terms and exceptions. Do not infer that section 12 establishes a blanket WCAG conformance obligation for every internal document or application.
- The Customer Service Standard (IASR Part IV.2, sections 80.45 to 80.51) and the Human Rights Code duty to accommodate may be relevant to the service, interaction, or accommodation request. Determine the specific duty and applicability before citing it.
- If a native application or document is also delivered as web content, assess the web publication and control context separately. Do not assume that the same legal hook applies to every delivery surface.
- Apply the Ontario Public Service (OPS) Digital Accessibility Standard (ODAS) only to products and content that fall within the standard's current scope. The standard is an OPS policy requirement, not legislation. Verify current coverage for mobile applications, documents, web applications, and web content before citing it.

## Technical interpretation and scope checks

- WCAG was written for web content. Use WCAG2ICT as an interpretation aid when applying relevant WCAG success criteria to non-web information and communications technology. Do not assume every web criterion applies unchanged to every format.
- Consider the applicable platform accessibility APIs and conventions for native applications, including accessible names, roles, states, keyboard or switch navigation, screen-reader output, focus behaviour, text scaling, and system accessibility settings.
- For documents, consider semantic structure, tagging, reading order, headings, links, table headers, language metadata, and text alternatives in the actual exported format.
- Some success criteria may be not applicable or may require adaptation in non-web contexts. Document the technical reason and the applicable interpretation source. Do not mark criteria as not applicable merely because they are inconvenient to test.
- For closed-functionality devices, such as certain kiosks and automated teller machines, where assistive technology cannot be attached, determine the equivalent built-in facilitation required by the applicable standard. WCAG does not assess hardware accessibility by itself.

## Citation guidance

Use the legal citation template in `SKILL.md`. Cite only the specific statutory provision that applies to the organisation and surface. Where an issue is based on WCAG2ICT, a platform standard, ODAS, a contract, or an organisational policy, identify that basis separately and do not mislabel it as an AODA statutory requirement.

## Sources

- AODA and IASR: https://www.ontario.ca/laws/regulation/110191
- Ontario accessibility guidance: https://www.ontario.ca/page/how-make-websites-accessible
- WCAG2ICT: https://www.w3.org/TR/wcag2ict/
- ODAS (GO-ITS 201PRS), for authorised OPS users: https://intra.ontario.ca/tbs/ops-digital-accessibility-standard-odas-html-version
