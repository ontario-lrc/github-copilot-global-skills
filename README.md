# GitHub Copilot Global Skills

Reusable procedures and supporting resources for GitHub Copilot in Visual Studio Code.

## Design

- **Agents** define the responsibility, authority, and tool boundaries for delegated work.
- **Skills** define how to perform a repeatable activity.
- **Instructions** provide concise cross-cutting or file-scoped rules.

Keep agent files short. Put detailed procedures in one focused `SKILL.md`, and bind only the relevant skill to each agent through the Copilot `skills` frontmatter. Copilot progressively loads skill descriptions, instructions, and referenced resources, so unrelated procedures need not be placed in every agent's context.

Each skill has a folder whose name matches the `name` in the `SKILL.md` frontmatter.

## General engineering skills

| Skill | Responsibility |
|---|---|
| `delegation-and-handoff` | Define bounded specialist assignments and coordinate hand-offs. |
| `structured-reporting` | Produce concise, evidence-based reports. |
| `repository-investigation` | Inspect and explain an existing repository. |
| `requirements-analysis` | Elicit, specify, and validate requirements. |
| `architecture-design` | Develop architecture and technical design decisions. |
| `implementation-workflow` | Implement, debug, and refactor approved changes. |
| `software-testing` | Plan, design, and execute risk-based tests. |
| `code-review` | Review code changes read-only. |
| `security-assessment` | Assess threats and security controls read-only. |
| `documentation-release` | Prepare technical and release documentation. |

## Domain-specific skills

| Skill | Responsibility |
|---|---|
| `accessibility-audit` | Assess accessibility, applicable Ontario requirements, and remediation options. |
| `add-ontario-design-system` | Integrate or upgrade the ODS distribution package in an existing web application. |
| `new-angular-app` | Create a new Angular application using the defined project workflow. |

## Agent-to-skill mapping

| Agent | Bound skills |
|---|---|
| `00 - Software Engineering Orchestrator` | `delegation-and-handoff`, `structured-reporting` |
| `10 - Codebase Explorer` | `repository-investigation` |
| `11 - Requirements Analyst` | `requirements-analysis` |
| `12 - Software Architect` | `architecture-design` |
| `20 - Implementation Engineer` | `implementation-workflow` |
| `30 - Test Engineer` | `software-testing` |
| `31 - Code Reviewer` | `code-review` |
| `32 - Security Reviewer` | `security-assessment` |
| `40 - Technical Documentation Specialist` | `documentation-release` |

Domain-specific skills remain independently discoverable or can be invoked explicitly when relevant. They are not preloaded into every agent.

## Installation

Copy the selected skill folders into the personal Copilot skills directory:

- Windows: `%USERPROFILE%\.copilot\skills`
- macOS/Linux: `~/.copilot/skills`

### Windows PowerShell

```powershell
$source = (Get-Location).Path
$destination = Join-Path $HOME '.copilot\skills'
New-Item -ItemType Directory -Force -Path $destination | Out-Null
Get-ChildItem -LiteralPath $source -Directory |
    Where-Object { Test-Path (Join-Path $_.FullName 'SKILL.md') } |
    ForEach-Object {
        Copy-Item -LiteralPath $_.FullName -Destination $destination -Recurse -Force
    }
```

Review local changes before overwriting a skill with the same name. Do not copy this repository's `README.md` into the skills directory.

## Maintenance

Keep descriptions distinctive and concise. Avoid duplicating global instructions or restating a bound skill inside an agent. Split a skill only when it contains genuinely independent workflows with different triggers or authority boundaries.

## Companion repositories

- [Global Agents](https://github.com/ontario-lrc/github-copilot-global-agents)
- [Global Instructions](https://github.com/ontario-lrc/github-copilot-global-instructions)
