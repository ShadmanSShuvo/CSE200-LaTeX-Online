# CSE200 LaTeX Online

This repository contains a set of standalone LaTeX write-ups for CSE200-style coursework. Each folder is its own mini project with a `main.tex` entry point, supporting source files, and its own bibliography. The documents are written as short, polished academic handouts rather than a single combined book.

## Project Layout

Each top-level folder can be compiled independently.

| Folder | Topic | Notes |
| --- | --- | --- |
| `A1-knot/` | Knot Theory | Multi-part article with shared `preamble.tex`, section files `1.tex` through `7.tex`, and `refs.bib`. |
| `A2-firefly/` | Fireflies in Union | Article on synchronization in fireflies, split across `1.tex` through `6.tex`, with `preamble.tex` and `firefly_refs.bib`. |
| `B1-laplace/` | Laplace Analysis and Applications | Self-contained article with `main.tex`, `laplace.bib`, and the helper script `rc_response.py`. |
| `B2-dna/` | DNA Data Storage | Self-contained article with figures, `main.tex`, and `dna_storage_refs.bib`. |
| `C1-riemann/` | The Riemann Hypothesis | Mathematical handout with table of contents, theorem-style formatting, and `riemann_hypothesis_refs.bib`. |
| `C2-solar/` | The Solar System | Illustrated article with planets, tables, and `solar_system.bib`. |

## What Is in Each Folder?

Most folders follow the same pattern:

- `main.tex` is the document entry point.
- `preamble.tex`, when present, holds shared packages, colors, and custom commands.
- `*.bib` stores references for `biblatex`.
- Additional `.tex` files split the write-up into manageable sections.
- Image files, when used, live beside the document they belong to.

This layout makes it easy to compile, edit, and grade one assignment at a time.

## Requirements

To build the documents, install a LaTeX distribution such as:

- TeX Live
- MacTeX on macOS
- MiKTeX on Windows

You will also need `biber`, because the documents use `biblatex` with the `biber` backend.

For the `B1-laplace/` folder, `python3` may be useful if you want to run the helper script `rc_response.py`.

## How to Compile

The easiest way is to use `latexmk` from inside the folder you want to build:

```bash
cd A1-knot
latexmk -pdf main.tex
```

Repeat the same pattern for any other folder:

```bash
cd A2-firefly
latexmk -pdf main.tex
```

If you prefer to compile manually, use this sequence for documents that depend on bibliographies:

```bash
pdflatex main.tex
biber main
pdflatex main.tex
pdflatex main.tex
```

The output PDF will be created in the same folder as `main.tex`.

## Suggested Workflow

1. Open the folder you want to work on.
2. Edit the relevant `.tex` files and any bibliography entries.
3. Rebuild the document with `latexmk -pdf main.tex`.
4. Check the PDF for layout issues, missing references, and figure placement.
5. Repeat until the document reads cleanly from start to finish.

## Notes for Students

- Keep each project self-contained so it can be compiled on its own.
- Use short section files when a document becomes long or easier to manage in pieces.
- Keep figure files in the same folder as the document that uses them.
- Re-run the build after changing citations, labels, or cross-references.

## Repository Purpose

The repository is organized as a collection of polished class-style handouts covering different mathematical and scientific topics. The focus is on clear presentation, structured exposition, and reproducible LaTeX builds.
