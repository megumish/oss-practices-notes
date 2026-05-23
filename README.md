# OSS Practices Notes

Personal notes from exploring OSS repositories, engineering practices, project
structures, and reusable patterns.

## Purpose

This repository is a place to study OSS projects and extract practical lessons
from them. It is not meant to be a universal best-practices guide. The goal is
to keep observations grounded in specific repositories while gradually building
more general notes across projects.

Each study should distinguish between:

- practices that seem broadly reusable
- practices that depend on a project's phase, domain, team, or toolchain
- practices that are useful only in the original repository's context
- open questions worth revisiting after looking at more projects

## Repository Structure

- `case-studies/`: notes on individual OSS repositories
- `notes/`: cross-project observations that emerge from multiple studies
- `skills/`: reusable skills for studying repositories and writing notes
- `templates/`: reusable templates for new repository studies

## Skills

- `oss-repository-study`: analyze an OSS or GitHub repository and write a
  grounded case study under `case-studies/`

## Current Studies

- [Karpathy-inspired agent guidelines](case-studies/2026-05-23-karpathy-inspired-agent-guidelines.md)

## How To Add A Study

1. Copy `templates/repository-study.md` into `case-studies/`.
2. Name the file with a date and short repository slug.
3. Keep repository-specific facts in the case study.
4. Move repeated themes into `notes/` only after they appear across multiple
   repositories or feel useful beyond a single project.

Suggested filename:

```text
case-studies/YYYY-MM-DD-owner-repo.md
```

## Study Lens

When exploring a repository, useful questions include:

- What problem does the project solve?
- Who appears to be the intended user?
- What is the project phase: exploration, foundation, feature growth,
  hardening, or maintenance?
- Which practices are encoded in docs, tests, tooling, CI, examples, or
  contribution workflows?
- Which practices are broadly reusable, and which are context-specific?
- What tradeoffs does the project seem to make?
- What would be risky to copy into another project without adaptation?

## Working Hypothesis

Good OSS practice notes should preserve context. A pattern is more useful when
the note explains where it worked, what constraints made it work, and where it
might fail.
