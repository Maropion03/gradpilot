# Gradpilot

Gradpilot is a reusable skill for graduate application strategy. It helps an agent or CLI turn scattered applicant information into a decision-ready recommendation for profile evaluation, school selection, SOP positioning, resume framing, and timeline planning.

The package is written to be host-agnostic first, with optional metadata for platforms that support richer skill registration.

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

### Codex-style hosts

Use:

- `SKILL.md` for the behavior contract
- `agents/openai.yaml` for display metadata
- `references/` for optional structured guidance

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

### Example 1: School selection

```text
Use Gradpilot to evaluate my profile for 2027 MSBA applications in the US.
My background: [resume or summary]
Target: balanced school list with reach / target / safety buckets.
```

### Example 2: SOP positioning

```text
Use Gradpilot to help me shape my SOP strategy for HCI master's programs.
Focus on the strongest narrative angle, weak points to reframe, and what evidence to emphasize.
```

### Example 3: Country comparison

```text
Use Gradpilot to compare UK, Hong Kong, and Singapore taught master's options for my profile.
Judge by fit, admission difficulty, ROI, and post-study path.
```

## Customization Notes

Gradpilot is intentionally conservative:

- default language is Chinese unless the user asks otherwise
- admission probabilities are directional planning bands, not predictions
- unrealistic targets should be recalibrated directly
- facts and inference should be clearly separated

If you adapt this skill for a specific market or institution type, keep the same decision discipline and only localize the program logic, examples, and terminology.
