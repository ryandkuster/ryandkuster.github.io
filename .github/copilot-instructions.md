# Copilot Instructions

## Project Overview

This is a Jekyll-based GitHub Pages site serving bioinformatics training documentation for UTK (University of Tennessee, Knoxville). Content covers HPC cluster usage (ISAAC), data transfer workflows, and computational biology tools.

## Local Development

```bash
# Serve locally (requires Bundler + Jekyll installed)
bundle exec jekyll serve
```

Before serving locally, switch `_config.yml` to use the local theme:
```yaml
# Comment out the remote_theme line:
# remote_theme: pmarsceill/just-the-docs

# Uncomment the local theme line:
theme: "just-the-docs"
```
Revert this change before pushing to GitHub — GitHub Pages uses `remote_theme`.

## Architecture

- **Theme**: [`just-the-docs`](https://github.com/pmarsceill/just-the-docs) via `remote_theme` in `_config.yml`
- **Markdown processor**: kramdown
- **Content sections**: each top-level directory (`ISAAC_training/`, `UTIACR_training/`) is a nav section with an `index.md` as the parent page and child pages for subtopics
- **Practice data**: `practice_data/` holds sample bioinformatics files (FASTQ, FASTA, GFF) used in training exercises

## Content Conventions

### Front Matter (required on every `.md` page)

```yaml
---
layout: default         # or "page" for standalone pages
title: Page Title
parent: Parent Title    # must match the parent page's `title` exactly
nav_order: 1            # controls sidebar order within a section
---
```

Top-level section index pages use additional keys:
```yaml
has_children: true
has_toc: false
permalink: /
heading_anchors: true
```

### Adding a new training section

1. Create a new directory (e.g., `new_training/`)
2. Add `new_training/index.md` with `has_children: true` and a unique `nav_order`
3. Add child pages with `parent: <index title>` matching exactly

### Callout/note style

Use blockquote + bold label for notes and warnings:
```markdown
> **_NOTE:_**  
> Your note text here.
```

### Code blocks

Fenced with triple backticks, no language specifier for shell commands shown to end users:
```
ssh <username>@login.isaac.utk.edu
```
Use angle-bracket placeholders (`<username>`, `</path/to/data/>`) for user-substituted values.
