# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this repo does

Generates Italian association meeting minutes (verbali di assemblea) as PDF documents. The workflow is:

1. Edit meeting data in `dati.yaml` (Mustache variables)
2. Edit the document structure in `docs/ASSEMBLEA.md` (Markdown with `{{variable}}` placeholders)
3. Push to `main` → GitHub Actions builds the PDF via Pandoc + XeLaTeX and deploys it to GitHub Pages as `latest.pdf`

The CI pipeline copies `docs/ASSEMBLEA.md` → `README.md` before building, so `README.md` in the root is auto-generated and should not be edited directly.

## Local build

Requirements: `pandoc` (3.x), `xelatex` (TeX Live or MacTeX), `pandoc-mustache` pip package, `fonts-liberation`.

```bash
# Install pandoc-mustache
pip install pandoc-mustache

# Build PDF locally (mirror what CI does)
cp docs/ASSEMBLEA.md README.md
pandoc --defaults styles/defaults.yml README.md -o output.pdf
```

## Architecture

| File | Purpose |
|------|---------|
| `dati.yaml` | All variable data for the meeting (names, dates, agenda items, votes) |
| `docs/ASSEMBLEA.md` | Document template — Markdown with `{{variable}}` Mustache placeholders |
| `styles/defaults.yml` | Pandoc configuration (engine: xelatex, filter: pandoc-mustache, template reference) |
| `styles/template.latex` | XeLaTeX template controlling layout, fonts (Liberation Sans), headers/footers |
| `styles/titlesec.sty` | Bundled LaTeX package for section title formatting |
| `styles/wrapfig.sty` | Bundled LaTeX package for figure wrapping |
| `.github/workflows/assembla_doc_template.yml` | CI pipeline: builds PDF, commits updated README.md, deploys to GitHub Pages |
| `.github/scripts/get_font.py` | Helper script to read font choice from `styles/config.yml` — **not currently wired into the workflow** and `styles/config.yml` does not exist; ignore unless adding font-switching support |

## CI details

The workflow runs inside `ghcr.io/dmgiulioromano/latex-docker-ubuntu:2026.1-small` (a custom image with TeX Live pre-installed). It installs Pandoc 3.x at runtime. The built PDF is published to GitHub Pages as `latest.pdf` and also uploaded as a timestamped workflow artifact (`verbale-assemblea.pdf-<TIMESTAMP>.pdf`).

## Template variable system

`dati.yaml` uses a flat key-value structure. Multi-line fields (participant lists, agenda) use YAML block scalars (`|`) since `pandoc-mustache` does not support loops — lists must be pre-formatted as Markdown strings.

The `---\nmustache: dati.yaml\n---` frontmatter at the top of `docs/ASSEMBLEA.md` tells `pandoc-mustache` which data file to use. The same file is referenced in `styles/defaults.yml` under `variables.mustache`.
