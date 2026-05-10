# Gradpilot Packaging Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Reposition the existing Gradpilot repository as a reusable skill package for broad agent and CLI usage without expanding its feature scope.

**Architecture:** Keep the package centered on `SKILL.md`, treat `README.md` as the public entry point, and keep host metadata isolated in `agents/openai.yaml`. Limit edits to wording, structure, and cross-file consistency.

**Tech Stack:** Markdown, YAML, Git

---

### Task 1: Rewrite the public entry document

**Files:**
- Modify: `README.md`

- [x] **Step 1: Replace the thin README with a host-agnostic package overview**

Write sections for positioning, use cases, input expectations, output modes, compatibility, repository structure, and examples.

- [x] **Step 2: Verify the README stays within current product scope**

Check that the README describes existing Gradpilot behavior and does not promise new features, platform integrations, or operational services.

### Task 2: Align the skill contract

**Files:**
- Modify: `SKILL.md`

- [x] **Step 1: Tighten wording around trigger conditions and boundaries**

Clarify when Gradpilot should be used, when it should not, and keep the package framed as strategy guidance.

- [x] **Step 2: Remove host-locked phrasing**

Keep the instructions reusable across agent and CLI environments while preserving the workflow and communication rules.

### Task 3: Align host metadata

**Files:**
- Modify: `agents/openai.yaml`

- [x] **Step 1: Update UI metadata to match the README and skill wording**

Keep the display name, short description, and default prompt aligned with the package positioning.

### Task 4: Validate and prepare the repository state

**Files:**
- Modify: `docs/superpowers/specs/2026-05-10-gradpilot-packaging-design.md`
- Modify: `docs/superpowers/plans/2026-05-10-gradpilot-packaging.md`

- [x] **Step 1: Add a minimal design record**

Save the approved packaging direction as a short spec document.

- [x] **Step 2: Add a minimal implementation plan record**

Save the scoped plan so the brainstorming flow has a concrete handoff artifact.

- [x] **Step 3: Self-review the final diff**

Read the changed files, confirm terminology alignment, and prepare a single commit for push.
