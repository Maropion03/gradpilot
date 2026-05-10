# Gradpilot Packaging Design

**Goal**

Polish the existing Gradpilot skill package so it reads as a reusable, host-agnostic skill repository for graduate-application strategy, while keeping the scope limited to the current package contents.

**Scope**

- Rewrite `README.md` for general skill users instead of a single host
- Align `SKILL.md` wording with the README
- Keep `agents/openai.yaml` consistent with the new positioning
- Do not expand Gradpilot into a broader counseling framework

**Design**

The repository should present `SKILL.md` as the behavioral source of truth, `references/` as optional structured support material, and `agents/openai.yaml` as host-specific metadata rather than the center of the package. The README should use a two-layer explanation: generic usage first, host-specific adaptation second.

The skill itself should stay focused on strategic application guidance: applicant snapshot, structured evaluation, output-track selection, and decision-ready recommendations. Wording that sounds tied to one runtime should be removed or softened so the package can be reused by other agents or CLIs with minimal adaptation.

**Non-Goals**

- Adding new references or new product capabilities
- Writing platform-specific installation guides for many frameworks
- Reworking the evaluation rubric or output templates
