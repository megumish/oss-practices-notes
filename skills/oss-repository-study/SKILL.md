---
name: oss-repository-study
description: Analyze an OSS or GitHub repository and write grounded study notes for this repository. Use when asked to investigate a repository, summarize its practices, compare what is reusable versus context-specific, extract engineering lessons, or add/update a case study under case-studies/.
---

# OSS Repository Study

## Overview

Analyze one OSS repository at a time and produce a grounded case study. Preserve
the difference between repository facts, your interpretation, reusable
practices, context-specific choices, risks when copying, and follow-up
questions.

## Workflow

1. Resolve the target repository.
   - Use the repository URL, `owner/repo`, or local checkout provided by the
     user.
   - If the target is ambiguous, ask for the repository before writing notes.

2. Gather evidence.
   - Inspect the README, docs, examples, contribution guide, tests, CI, release
     workflow, package metadata, and directory structure when available.
   - Prefer primary repository sources over third-party summaries.
   - For current remote repository facts, verify against GitHub or the web when
     local files are not enough.

3. Classify the project context.
   - Identify the apparent purpose, intended users, primary artifact, language
     or toolchain, and project phase.
   - Use cautious phase labels such as exploration, foundation, feature growth,
     hardening, or maintenance. Mark uncertain labels as hypotheses.

4. Extract practices.
   - Look for practices encoded in docs, tests, examples, CI, release process,
     architecture, contribution workflow, issue templates, or community norms.
   - Separate practices that seem broadly reusable from practices tied to the
     project's domain, phase, team, ecosystem, or toolchain.
   - Note risks when copying a practice into another project without adapting
     it.

5. Write or update a case study.
   - Use `templates/repository-study.md` as the base structure.
   - Put repository-specific notes under `case-studies/`.
   - Name new files as `YYYY-MM-DD-owner-repo.md`.
   - Keep cross-project conclusions out of `notes/` until they are supported by
     more than one case study or clearly useful beyond a single project.

6. Verify the note.
   - Confirm links, repository names, and dates.
   - Check that facts and interpretations are not mixed together.
   - Check that the takeaway is narrower than the evidence.

## Writing Rules

- Keep the tone concise and analytical.
- Do not praise or criticize a project generically; explain concrete tradeoffs.
- Do not generalize from one repository too quickly.
- Prefer "seems", "appears", or "hypothesis" when evidence is incomplete.
- Preserve context: where the practice works, why it works there, and where it
  may fail.
- Mention unresolved questions instead of filling gaps with speculation.

## Output Expectations

When creating a case study, include at least:

- repository identity and date studied
- what the project is
- project context
- practices observed
- what seems reusable
- what seems context-specific
- risks when copying
- takeaway
- follow-up questions

When updating an existing study, keep the existing structure unless the change
requires a new section.
