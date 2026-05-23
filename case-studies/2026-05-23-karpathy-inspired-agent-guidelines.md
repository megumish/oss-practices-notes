# Karpathy-Inspired Agent Guidelines

## Repository

- Repository: `multica-ai/andrej-karpathy-skills`
- Date studied: 2026-05-23
- Topic: coding-agent behavior guidelines

## What It Is

This repository packages behavioral guidelines for coding agents across Claude
Code, Cursor, and skill/plugin formats. The core ideas are meant to reduce
common LLM coding mistakes:

- surface assumptions instead of silently guessing
- keep changes scoped
- avoid over-engineering
- verify the result with concrete checks

## What Seems Reusable

These ideas generalize beyond the original repository:

- State assumptions when a request is ambiguous.
- Keep changes tied to the requested outcome.
- Follow existing project patterns before introducing new abstractions,
  dependencies, or styles.
- Avoid speculative flexibility.
- Verify changes with an appropriate check.

These are especially valuable for existing codebases, where uncontrolled
changes increase cognitive load, make the system harder to understand, and can
expand the attack surface.

## What Seems Context-Specific

The guidance is intentionally conservative. That makes it strong for
maintenance work and feature work in existing codebases, but it may be too
restrictive if applied unchanged to:

- greenfield development
- research prototypes
- exploratory product work
- research-heavy OSS projects

In those contexts, the right practice may be phase-aware rather than always-on.

## Phase-Aware Interpretation

Instead of putting every rule into permanent project instructions or
contribution guides, some practices may work better as temporary operating
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

## Takeaway

The repository is useful as a compact set of conservative coding-agent
practices. For broader OSS exploration, the more general lesson is that
practices should be evaluated against project phase and context before being
copied into another project.

## Follow-Up Questions

- Should phase-aware practices be documented as project guidance, reusable
  skills, or task-specific prompts?
- How much of this guidance applies to non-agent OSS maintenance?
- Which practices remain useful as coding models improve?
