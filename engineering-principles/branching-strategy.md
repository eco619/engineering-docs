# Branching Strategy

Branching should support controlled engineering evolution.

Branches within eco619 should organize work in a way that protects stable documentation and code while allowing new engineering ideas, revisions, and platform capabilities to develop safely.

The objective is to keep the main branch stable, understandable, and representative of the current engineering baseline.

---

# Overview

This standard defines how branches should be created, named, used, reviewed, and merged across eco619 repositories.

It applies to:

- Documentation repositories
- Platform repositories
- Research repositories
- Future eco619 engineering projects

---

# Branching Principles

Branches should represent meaningful engineering work.

General principles include:

- Keep the main branch stable.
- Use branches for focused engineering changes.
- Avoid combining unrelated work into one branch.
- Name branches clearly.
- Merge only after the work is complete enough to preserve repository quality.
- Delete branches after they are merged when practical.
- Complete work within a branch before beginning unrelated engineering changes.

---

# Primary Branches

## main

The `main` branch represents the current approved engineering baseline for the repository.

Content in `main` should be stable, reviewed, and suitable for reference by future contributors.

The `main` branch should not be used for experimental work.

---

# Branch Types

Branch types should align with the commit types defined in the Git Commit Standard whenever practical, providing consistency between engineering work and repository history.

Branch types define the purpose of engineering work within a repository and should remain focused on a single engineering objective whenever practical.

Common branch types include:

- docs        Documentation changes
- feat        New platform capability
- fix         Correct an engineering issue
- refactor    Improve internal structure
- test        Add or improve testing
- research    Exploratory engineering work
- config      Configuration changes
- chore       Repository maintenance

---

# Branch Naming Format

Branches should follow this format:

```text
<type>/<short-description>

Branch names should be lowercase and use hyphens (-) to separate words.

For example:

docs/engineering-documentation-standard
feat/document-intelligence
fix/ocr-empty-page-detection
```
# Engineering Philosophy

Branching is part of engineering control.

A well-defined branching strategy separates stable engineering knowledge from active development, experimentation, and future platform evolution.

Branches should make engineering progress easier to understand, review, trace, and preserve throughout the life of the platform.

Technology should support human judgment. It should never replace it.
