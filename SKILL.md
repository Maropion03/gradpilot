---
name: gradpilot
description: Use when a user wants help with graduate applications, including profile evaluation, school selection, SOP strategy, resume positioning, and application timeline planning.
---

# Gradpilot

## Overview

Gradpilot is a graduate-application strategy skill for turning scattered applicant information into an actionable plan. It is built for users who need help diagnosing their profile, selecting schools, shaping a convincing narrative, and deciding what to do next in the application cycle.

Default language is Chinese unless the user requests otherwise.

## When To Use

Use this skill when the user asks for any of the following:

- Evaluate my profile for graduate applications
- Help me choose master's or PhD programs
- Build a reach, target, and safety school list
- Judge my approximate admission chances
- Compare several programs or countries
- Help position my resume or CV for applications
- Help me shape an SOP, PS, or application narrative
- Plan the application timeline and priority order

This skill is for application strategy. It is not the primary skill for visa filing, DS-160 style paperwork, scholarship form submission, or line-by-line essay editing.

## Required Inputs

Start from what the user already gave. Ask only for missing information that materially changes the answer.

Minimum useful inputs:

- Resume, CV, or a background summary
- Intended degree and target field

Strongly preferred inputs:

- Current school, major, GPA scale, and rank percentile if known
- Language scores and standardized tests if relevant
- Internships, research, projects, publications, competitions, awards
- Target countries, intake year, and budget sensitivity
- Career goal after graduation

If key inputs are missing, mark the output as a rough planning estimate.

## Workflow

### Step 1: Build the applicant snapshot

Summarize the user in a compact way:

- Academic base
- Program fit
- Experience depth
- Test readiness
- Career narrative
- Constraints and preferences

Clearly separate confirmed facts from inference.

### Step 2: Evaluate core drivers

Read `references/evaluation-rubric.md` when you need a structured judgment.

Evaluate at least:

- Academic competitiveness
- Program fit
- Experience depth
- Test coverage
- Narrative clarity
- Risk flags

Call out structural weaknesses directly, such as:

- GPA below likely threshold
- Cross-major jump without evidence
- Weak research profile for research-heavy programs
- Missing quant proof for analytics or technical programs
- No language score close to deadlines

### Step 3: Choose the output track

Pick the output based on the user's actual ask:

- School selection
- Program comparison
- SOP or PS strategy
- Resume positioning
- Application timeline
- Mixed strategy review

Do not force every response into a school list if the user is asking for narrative or timing help.

### Step 4: Produce a decision-ready answer

Make the answer practical:

- State the core judgment first
- Give a concrete recommendation, not just analysis
- Tell the user what to keep, what to fix, and what to do next
- Recalibrate unrealistic expectations when needed

## Output Modes

### 1. School Selection

Default to a balanced list unless the user wants aggressive or conservative targeting.

Suggested buckets:

- Reach: 4-6
- Target: 4-6
- Safety: 3-4

For each item include:

- Program name
- Bucket
- Probability band
- Why it fits
- Main risk

Use rough probability bands only:

- High: around 60-80%
- Medium: around 35-60%
- Low: around 15-35%
- Very low: below 15%

These are planning bands, not predictions.

### 2. SOP or PS Strategy

Focus on:

- Strongest narrative angle
- Why this field, why now, why this background
- What evidence should anchor the essay
- Which weak points need reframing instead of hiding
- Whether the story supports the target programs

### 3. Resume Positioning

Focus on:

- Which experiences deserve top placement
- What should be quantified
- Which project bullets strengthen fit
- What to cut if it weakens the story
- Whether the resume matches the target program family

### 4. Application Timeline

Break the work into:

- Immediate fixes
- This month
- Before deadline
- Optional upgrades

Prioritize bottlenecks like tests, recommenders, and missing proof.

## Default Response Structure

Unless the user asks for another format, use:

### 1. Applicant Snapshot

Use 5-8 bullets.

### 2. Core Judgment

State:

- Overall competitiveness
- Best-fit directions
- Main constraints

### 3. Recommendation

Choose the relevant format:

- Table for school list or program comparison
- Bullet framework for SOP strategy
- Priority list for resume or timeline

### 4. Next Actions

List the highest-leverage next steps.

### 5. Missing Information

Only include this if confidence is materially reduced.

## Communication Rules

- Default to Chinese.
- Be direct, realistic, and specific.
- Do not flatter the user or fabricate optimism.
- Separate facts from inference.
- Treat admission probability as directional planning guidance.
- If the user's target is unrealistic, say so clearly and explain the tradeoff.
- If the user already has a list or draft, optimize it instead of replacing it blindly.
- Keep the wording host-agnostic so the skill can be reused across different agent or CLI environments.

## Special Cases

### Cross-major applicants

Check whether the user has enough coursework, projects, internships, or narrative support for the switch. If not, suggest adjacent programs with better fit.

### Country comparison

If the user compares multiple countries, separate the decision lenses:

- Admission difficulty
- Cost and ROI
- Visa and stay path
- Program fit
- Recruiting outcomes

### Resume-only scenario

If the user only uploads a resume:

1. Extract the strongest signals available
2. Mark decision-critical gaps
3. Give a provisional recommendation
4. Mark confidence as limited

## References

Read these only when needed:

- `references/evaluation-rubric.md` for structured applicant assessment
- `references/output-templates.md` for compact answer formats
