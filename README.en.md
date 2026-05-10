<div align="center">

# Gradpilot

### A reusable graduate application strategy skill for agents and CLIs

Turn scattered applicant information into decision-ready guidance for profile evaluation, school selection, SOP positioning, resume framing, and application planning.

> Built for realistic application strategy, not vague encouragement.

![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)
![Skill Type](https://img.shields.io/badge/Type-Strategy%20Skill-7c3aed)
![Use Case](https://img.shields.io/badge/Use%20Case-Graduate%20Applications-2563eb)
![Host](https://img.shields.io/badge/Host-Agent%20%7C%20CLI-0f766e)

[中文](./README.md) · [English](./README.en.md)

[Install](#quick-install) · [Why](#why-gradpilot) · [Features](#what-gradpilot-helps-with) · [Use Cases](#when-to-use) · [Compatibility](#host-compatibility) · [Examples](#quick-usage-examples)

</div>

## Quick Install

### Codex

macOS / Linux

```bash
git clone git@github.com:Maropion03/gradpilot.git ~/.codex/skills/gradpilot
```

Windows PowerShell

```powershell
git clone git@github.com:Maropion03/gradpilot.git $HOME\.codex\skills\gradpilot
```

### Claude Code

macOS / Linux

```bash
git clone git@github.com:Maropion03/gradpilot.git ~/.claude/skills/gradpilot
```

Windows PowerShell

```powershell
git clone git@github.com:Maropion03/gradpilot.git $HOME\.claude\skills\gradpilot
```

Use `SKILL.md` as the main instruction file. Load `references/` only when you need the rubric or output templates.

<details>
<summary>Other host install paths</summary>

Clone into a custom target:

```bash
git clone git@github.com:Maropion03/gradpilot.git <TARGET>
```

Suggested targets:

| Host | macOS / Linux | Windows PowerShell |
|---|---|---|
| Codex | `~/.codex/skills/gradpilot` | `$HOME\.codex\skills\gradpilot` |
| Claude Code | `~/.claude/skills/gradpilot` | `$HOME\.claude\skills\gradpilot` |
| Generic custom host | your host's local skills or prompts directory | your host's local skills or prompts directory |
| Standalone prompt bundle | any reusable prompt directory | any reusable prompt directory |

Download only the core file instead of cloning:

```bash
mkdir -p gradpilot
cd gradpilot
curl -O https://raw.githubusercontent.com/Maropion03/gradpilot/main/SKILL.md
mkdir -p references
curl -o references/evaluation-rubric.md https://raw.githubusercontent.com/Maropion03/gradpilot/main/references/evaluation-rubric.md
curl -o references/output-templates.md https://raw.githubusercontent.com/Maropion03/gradpilot/main/references/output-templates.md
```

</details>

## Why Gradpilot

Most graduate-application advice is either too generic to act on or too optimistic to trust. Gradpilot is built to be more useful in the actual decision loop:

- It separates facts from inference instead of hiding weak assumptions.
- It treats school selection as a portfolio decision, not a dream-list exercise.
- It focuses on narrative credibility, not just surface-level resume polishing.
- It gives directional probability bands for planning, without pretending to predict admissions.
- It tells the user what to fix next, not just what sounds nice.

The goal is straightforward: help an agent or CLI produce realistic, decision-ready guidance for applicants who need clarity more than encouragement.

## What Gradpilot Helps With

- Profile diagnosis for master's or PhD applications
- Reach / target / safety school selection
- Program and country comparison
- SOP / PS narrative strategy
- Resume positioning for application fit
- Application timeline and priority planning

## When To Use

Use Gradpilot when the user wants judgment, prioritization, or strategy for graduate applications.

Typical prompts:

- "Evaluate my background for MS in Business Analytics."
- "Help me build a US / UK school list."
- "Compare these programs and tell me which fit is real."
- "Help me position my resume and SOP story."
- "What should I fix first before this intake?"

## When Not To Use

Gradpilot is not the primary workflow for:

- Visa filing or immigration forms
- DS-160 style operational paperwork
- Scholarship portal form filling
- Line-by-line essay polishing
- General career coaching unrelated to graduate applications

## What Inputs Work Best

Minimum useful inputs:

- Resume, CV, or a short background summary
- Intended degree and target field

Strongly preferred inputs:

- Current school, major, GPA scale, and rank percentile
- Language scores and standardized tests
- Internships, research, projects, publications, awards
- Target countries, intake year, and budget sensitivity
- Career goal after graduation

If critical inputs are missing, Gradpilot should still respond, but label the result as a rough planning estimate.

## Output Modes

Gradpilot does not force one format for every query. It should choose the output track that matches the user's ask:

- School selection
- Program comparison
- SOP / PS strategy
- Resume positioning
- Application timeline
- Mixed strategy review

The default answer shape is:

1. Applicant snapshot
2. Core judgment
3. Recommendation
4. Next actions
5. Missing information, only when confidence is materially reduced

## Host Compatibility

### Generic agent or CLI

Treat `SKILL.md` as the source of truth. A host only needs to:

1. Load the skill instructions
2. Inject them into the agent context
3. Optionally expose the reference files when deeper structure is needed

If your environment supports custom slash commands, prompt libraries, or named skills, register Gradpilot as a reusable strategy skill for graduate-application tasks.

### Codex / Claude Code style local skill hosts

Use:

- `SKILL.md` for the behavior contract
- `agents/openai.yaml` for display metadata
- `references/` for optional structured guidance

In practice:

- `Codex`
  - macOS / Linux: `~/.codex/skills/gradpilot`
  - Windows PowerShell: `$HOME\.codex\skills\gradpilot`
- `Claude Code`
  - macOS / Linux: `~/.claude/skills/gradpilot`
  - Windows PowerShell: `$HOME\.claude\skills\gradpilot`

### Other agent frameworks

If the host does not support a native skill system, the same package still works as:

- a reusable system prompt
- a prompt template bundle
- a task-specific instruction preset

The main requirement is preserving the workflow and communication rules from `SKILL.md`.

## Repository Structure

- `SKILL.md` - core instructions and workflow
- `references/evaluation-rubric.md` - structured evaluation lenses
- `references/output-templates.md` - compact answer shapes
- `agents/openai.yaml` - optional UI metadata for hosts that support it

## Quick Usage Examples

### Card 1: Start with school-list targeting

Best when the user has a basic profile and wants a fast reach / target / safety structure.

```text
Use Gradpilot to evaluate my background for 2027 master's applications in [country].

My profile:
- School / major:
- GPA / rank:
- Tests:
- Internships / research / projects:

Target:
- Field:
- Countries:
- Preference: balanced list

Please return:
1. applicant snapshot
2. reach / target / safety school list
3. top risks
4. next fixes
```

### Card 2: Start with SOP direction

Best when the background is decent but the story is still unstable and needs a credible narrative angle first.

```text
Use Gradpilot to help me shape my SOP strategy for [program family].

My background:
- Current major:
- Key experiences:
- Why I want to switch / continue:
- Career goal:

Please focus on:
1. strongest narrative angle
2. weak points that need reframing
3. evidence to emphasize
4. programs this story supports best
```

### Card 3: Start with country or program comparison

Best when the user has narrowed the options down and needs to judge which path fits best.

```text
Use Gradpilot to compare these options for my profile:
- Option A:
- Option B:
- Option C:

My background:
- School / major:
- GPA:
- Experience:
- Career goal:

Judge by:
1. fit
2. admission difficulty
3. ROI
4. post-study path
5. main tradeoff
```

## Customization Notes

Gradpilot is intentionally conservative:

- default language is Chinese unless the user asks otherwise
- admission probabilities are directional planning bands, not predictions
- unrealistic targets should be recalibrated directly
- facts and inference should be clearly separated

If you adapt this skill for a specific market or institution type, keep the same decision discipline and only localize the program logic, examples, and terminology.
