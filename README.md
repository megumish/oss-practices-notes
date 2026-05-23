# OSS Practices Notes

Personal notes on OSS projects, engineering practices, and reusable patterns.

## Purpose

This repository collects observations from exploring OSS projects. It is not
intended to be a universal rulebook. The goal is to separate practices that are
broadly useful from practices that depend on a project phase, team style,
domain, toolchain, or the current behavior of a specific technology.

## Case Study: Karpathy-Inspired Agent Guidelines

Repository explored:

- `multica-ai/andrej-karpathy-skills`

This repository packages behavioral guidelines for coding agents across Claude
Code, Cursor, and skill/plugin formats. Although the subject is AI coding
agents, some of its ideas generalize to OSS maintenance and engineering
practice:

- surface assumptions instead of silently guessing
- keep changes scoped
- avoid over-engineering
- verify the result with concrete checks

These are especially valuable for existing codebases, where uncontrolled
changes increase cognitive load, make the system harder to understand, and can
expand the attack surface.

## Initial Takeaway

The guidelines are useful, but conservative. They are strongest when applied to
maintenance work or feature work in an existing codebase.

For greenfield development, research prototypes, exploratory product work, or
research-heavy OSS, the same rules may be too restrictive if applied as
permanent project instructions. In those cases, phase-aware practices may work
better.

## Minimal Always-On Practices

These practices seem broadly useful across phases:

- State assumptions when the request is ambiguous. Ask only when a wrong
  assumption would be costly.
- Keep changes scoped to the requested outcome.
- Follow existing project patterns before introducing new abstractions,
  dependencies, or styles.
- Avoid speculative flexibility. Add only what the current request needs.
- Verify the result with the smallest relevant check, and report what was
  checked.

## Phase-Aware Practices

Instead of putting all rules into permanent project instructions or contribution
guides, phase-specific practices may be better treated as temporary operating
modes.

### Exploration

- Build the smallest runnable version that tests the main assumption.
- Optimize for learning rather than completeness.
- Mark throwaway code explicitly.

### Foundation

- Define core domain concepts and module boundaries early.
- Choose one pattern for state, data access, errors, and configuration.
- Avoid introducing multiple ways to do the same thing.

### Feature Work

- Add features in small vertical slices.
- Reuse established local patterns before creating new abstractions.
- Abstract only after a pattern repeats.

### Hardening

- Delete unused code, dependencies, routes, and configuration.
- Validate external inputs at system boundaries.
- Test core workflows and known failure modes.
- Review permissions, secrets, network calls, file access, and integrations.

### Maintenance

- Keep changes scoped.
- Avoid speculative flexibility.
- Verify each change and report what was checked.

## Working Hypothesis

For OSS exploration, the most useful setup may be:

1. Keep a very small set of always-on principles.
2. Treat phase-specific behavior as an explicit mode, not as permanent doctrine.
3. Explicitly choose the current project or task phase when evaluating a
   practice.
4. Revisit the phase at major milestones, such as prototype completion, MVP
   readiness, or pre-release hardening.

This keeps practices useful without making early exploration unnecessarily
rigid.
