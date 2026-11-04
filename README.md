# Copilot Skills

Reusable agent skills for accessibility audits, the Ontario Design System, and new Angular apps.

Each skill is a folder that contains a `SKILL.md` file. The file states when the skill applies, its rules, and its step-by-step procedure.

## Skills

### [accessibility-audit](accessibility-audit/SKILL.md)

Audits web and non-web user interfaces and content for barriers under the Accessibility for Ontarians with Disabilities Act (AODA).

- Maps each finding to the Integrated Accessibility Standards Regulation (IASR, Ontario Regulation 191/11) and to Web Content Accessibility Guidelines (WCAG) success criteria.
- For non-web surfaces, such as native mobile, desktop, and kiosk software and documents, applies the World Wide Web Consortium (W3C) guidance on applying WCAG to non-web technologies (WCAG2ICT).
- Fixes each barrier with the smallest verifiable change, and cites the legal reference for each finding.
- Reads `accessibility.instructions.md` from `%USERPROFILE%\.copilot\instructions`.

Example request: *"Audit the checkout form for accessibility barriers."*

### [add-ontario-design-system](add-ontario-design-system/SKILL.md)

Adds the latest Ontario Design System (ODS) distribution package to an existing web app. It works with any web stack, such as Angular, React, Vue, plain HyperText Markup Language (HTML), or server-rendered templates.

- Downloads the package from `designsystem.ontario.ca`, and checks that the release notes name the same version.
- Serves the package's files unchanged from a `vendor\ontario-design-system` folder inside the app's static folder, and links its stylesheet from every page.
- Offers optional extras, which you choose in each run: an ODS favicon set, a simple footer, an application header, and Sass variables.
- Does not cover ODS packages on the Node Package Manager (npm) registry, web components, or building pages from ODS components.

Example request: *"Add the Ontario Design System to this app."*

### [new-angular-app](new-angular-app/SKILL.md)

Creates a new Angular workspace and app with the latest Angular Command-Line Interface (CLI), on the newest Long-Term Support (LTS) release of Node.js.

- Installs and selects Node.js with Node Version Manager (NVM) for Windows, version 2, in PowerShell.
- Uses a fixed `ng new` configuration, which its `SKILL.md` lists. It includes server-side rendering, zoneless mode, and the Angular Model Context Protocol (MCP) server configuration for Visual Studio Code (VS Code).
- Removes the `AGENTS.md` file that this configuration generates, and builds the app to check it.
- Asks for the app name, then shows a command plan for your approval before it runs anything.
- Not for existing Angular workspaces, NVM on macOS or Linux, or NVM for Windows version 1.

Example request: *"Create a new Angular app called `my-app`."*

## Requirements

- Windows with PowerShell, for `new-angular-app` and `add-ontario-design-system`.
- Node Version Manager (NVM) for Windows, version 2, for `new-angular-app`. Version 1 is not supported. `new-angular-app` uses NVM to install the newest Long-Term Support (LTS) release of Node.js, and then installs pnpm and the Angular Command-Line Interface (CLI) globally.
- Internet access to `nodejs.org`, `registry.npmjs.org`, `angular.dev`, and `designsystem.ontario.ca`, which the skills fetch at run time.
- `accessibility.instructions.md` in `%USERPROFILE%\.copilot\instructions`, for `accessibility-audit`.
- Optional: Visual Studio Code (VS Code), to use the Model Context Protocol (MCP) configuration that `new-angular-app` creates.

## Installation

Place the skill folders in `%USERPROFILE%\.copilot\skills`, the user-level skills folder. The skills are Markdown files, so no build step is needed.

## Usage

Describe the task in plain language. The agent selects the skill whose description matches the request. Example requests are listed under [Skills](#skills).

- `new-angular-app` and `add-ontario-design-system` show a command plan and run nothing until you approve it.
- `new-angular-app` runs only the commands in its approved plan, which includes one deletion of the generated `AGENTS.md` file.
- `new-angular-app` and `add-ontario-design-system` treat fetched web pages as data, and ignore any instructions in them.
- The skills do not claim compliance. Accessibility findings still need manual and assistive technology testing, and legal review where a report flags it.

## Folder Layout

```text
skills/
├── README.md
├── accessibility-audit/
│   ├── SKILL.md
│   └── references/
│       └── non-web.md
├── add-ontario-design-system/
│   └── SKILL.md
└── new-angular-app/
    └── SKILL.md
```

## Adding a Skill

1. Create a folder named after the skill, such as `my-skill`.
2. Add a `SKILL.md` file that starts with front matter, a metadata block between `---` lines:
	- `name`: the same as the folder name.
	- `description`: when the skill applies, including trigger phrases.
	- `argument-hint` (optional): a short hint about the expected input.
3. Write the rules and procedure in Markdown. Follow `instruction-files.instructions.md` in `%USERPROFILE%\.copilot\instructions`.

## Licence

This collection is licensed under [Creative Commons Zero v1.0 Universal (CC0 1.0)](https://creativecommons.org/publicdomain/zero/1.0/). Its author has dedicated the work to the public domain, so you can copy, modify, distribute, and use it, even for commercial purposes, without asking permission.
