# GitHub Copilot Global Skills

Reusable, technology-agnostic workflows and supporting resources for GitHub Copilot.

## Design
Skills define **how to perform a repeatable activity**. Agents define who owns the work and what authority they have. Global instructions provide concise cross-cutting defaults. Skills should be loaded only when relevant; avoid explicitly preloading large skills into every agent.

Each skill is a folder containing a `SKILL.md`. Add supporting reference files only when the procedure genuinely needs them. Keep the skill description specific so Copilot can discover it for appropriate tasks.

## Skills
| Skill | Purpose |
|---|---|
| engineering-baseline | Shared engineering checklist |
| delegation-and-handoff | Focused specialist assignments and handoffs |
| structured-reporting | Concise summaries and formal reporting |
| repository-investigation | Repository discovery and tracing |
| requirements-analysis | Requirements and acceptance criteria |
| architecture-design | Architecture and technical design |
| implementation-workflow | Implementation, debugging, and refactoring |
| software-testing | Risk-based test design and execution |
| code-review | Read-only code review |
| security-assessment | Threat analysis and security assessment |
| documentation-release | Documentation and release preparation |

Existing domain-specific skills, including accessibility, Ontario Design System, and Angular setup skills, remain separate and should be retained.

## Installation

Copy skill directories into the user-level skills directory. This merges the selected skill folders and does not delete unrelated local skills.

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

### macOS / Linux
```bash
destination="$HOME/.copilot/skills"
mkdir -p "$destination"
for skill in */; do
    [ -f "${skill}SKILL.md" ] || continue
    cp -R "$skill" "$destination/"
done
```

Review local edits before overwriting matching skill files.

## Companion repositories
- [Global Agents](https://github.com/ontario-lrc/github-copilot-global-agents)
- [Global Instructions](https://github.com/ontario-lrc/github-copilot-global-instructions)