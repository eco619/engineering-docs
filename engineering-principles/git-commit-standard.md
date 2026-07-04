# Git Commit Standard

A consistent commit history is part of the engineering record.

Git commits should document meaningful engineering progress rather than simply record file modifications.

The objective is to maintain a commit history that documents the chronological evolution of the platform, allowing future contributors to understand how the architecture, documentation, and implementation matured over time.

---

# Overview

This standard defines how commit messages should be written across all eco619 repositories.

It promotes consistency throughout the engineering ecosystem while preserving the reasoning behind architectural decisions, engineering decisions, and platform evolution.

This standard applies to:

- Documentation repositories
- Platform repositories
- Research repositories
- Future eco619 engineering projects

---

# Engineering Principles

Every commit should represent a meaningful engineering change that advances the documented evolution of the platform.

General principles include:

- Use clear and concise commit messages.
- Describe the engineering intent of the change.
- Write commit messages in the present tense.
- Keep the first line under approximately 72 characters whenever practical.
- Make one meaningful engineering change per commit whenever practical.
- Avoid vague messages such as `update`, `changes`, `fix stuff`, or `misc`.
- A commit should explain **why** the engineering change was made, not merely **what** files changed.

---

# Commit Format

```text
<type>(<category>): <description>
```

Example:

```text
docs(architecture): Add Platform Architecture v1.0
```

---

# Commit Types

## docs

Documentation changes.

Examples:

```text
docs(architecture): Add Platform Architecture v1.0
docs(ip): Update Intellectual Property Register
docs(principles): Add Engineering Principles
docs(readme): Update engineering overview
docs(research): Add OCR evaluation framework
docs(roadmap): Update platform roadmap
```

---

## feat

Introduces a new platform capability.

Examples:

```text
feat(ai-provider): Add provider selection support
feat(document-intelligence): Add PDF enrichment pipeline
feat(visual-intelligence): Add object recovery queue
```

---

## fix

Corrects an engineering issue or unintended behavior.

Examples:

```text
fix(metadata): Correct timestamp parsing
fix(ocr): Handle empty page detection
fix(summary): Preserve source references
```

---

## refactor

Improves internal structure without changing intended behavior.

Examples:

```text
refactor(ai-provider): Simplify provider abstraction
refactor(records): Consolidate derived record creation
```

---

## test

Adds or improves testing.

Examples:

```text
test(verification): Expand claim validation coverage
test(visual): Add handwritten annotation tests
```

---

## perf

Improves performance.

Examples:

```text
perf(database): Optimize relationship queries
perf(pdf): Improve large document processing
```

---

## config

Updates platform configuration.

Examples:

```text
config(ollama): Update default model selection
config(project): Add project configuration options
```

---

## security

Improves platform security.

Examples:

```text
security(config): Remove exposed local paths
security(storage): Improve credential handling
```

---

## chore

Maintenance that does not change platform behavior.

Examples:

```text
chore(github): Update repository settings
chore(repository): Reorganize documentation folders
```

---

## style

Formatting or presentation changes that do not affect functionality.

Examples:

```text
style(documentation): Improve heading consistency
style(readme): Standardize formatting
```

---

## build

Changes related to build systems or dependency management.

Examples:

```text
build(project): Update dependency versions
build(repository): Improve build configuration
```

---

## ci

Changes related to continuous integration or deployment automation.

Examples:

```text
ci(github): Update GitHub Actions workflow
ci(repository): Improve automated validation
```

---

# Recommended Categories

Categories should describe the primary engineering area affected by the commit.

Categories should remain stable over time and represent long-lived areas of the engineering architecture rather than temporary implementation details.

Common categories include:

- ai-provider
- architecture
- communication-intelligence
- conversation
- document-intelligence
- documentation
- github
- ip
- knowledge
- metadata
- ocr
- pdf
- principles
- project
- readme
- records
- repository
- research
- roadmap
- verification
- visual-intelligence

Additional categories may be introduced as the engineering architecture evolves.

---

# Versioned Engineering Documents

Formal engineering documents should include a version number when establishing or updating an engineering baseline.

Examples:

```text
docs(architecture): Add Platform Architecture v1.0
docs(architecture): Update Platform Architecture v1.1
docs(architecture): Publish Knowledge Evolution v2.0
```

Version numbers should be used only when the document represents a formal engineering baseline or significant architectural milestone.

---

# Commit Size

## Engineering Rule 1

One meaningful engineering change should normally result in one commit.

Good:

```text
docs(architecture): Add Platform Architecture v1.0
```

Less useful:

```text
docs: Add files
```

A single commit may include multiple files when they all contribute to the same engineering change.

---

# Extended Descriptions

Most commits require only a concise summary.

Use an extended description when documenting:

- Major architectural changes
- Significant engineering decisions
- Breaking changes
- Security-related changes
- Changes affecting multiple repositories or platforms

If the summary fully explains the engineering change, an extended description is not required.

---

# Engineering Philosophy

Git history is part of the engineering record.

Every commit contributes to the documented evolution of the platform. A well-maintained commit history should enable future engineers to understand not only **what** changed, but also **why** it changed and how the platform evolved over time.

Engineering documentation should preserve design intent with the same level of care as implementation details.

A disciplined commit history is not merely a development practice—it is part of the engineering record.

Technology should support human judgment. It should never replace it.
