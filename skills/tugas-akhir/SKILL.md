---
name: tugas-akhir
description: Create a Medical Technology ITS thesis project, write its proposal or thesis, or check its PDF.
---

# Medical Technology ITS thesis

Resolve `template/` relative to this SKILL.md; work in the user's workspace.

## Start a project

If a thesis project exists, use it. Otherwise, show the destination and obtain consent before copying `<skill-directory>/template/.` into an empty directory. Confirm `sempro.tex`, `buku-ta.tex`, `bab/`, and `pustaka/variables.tex` exist.

## Write

Identify the requested section and available study data and sources. Find metadata in `pustaka/variables.tex`, abstracts in `abstrak/`, chapters in `bab/`, and references in `pustaka/pustaka.bib`; chapters 1–3 serve both documents. Use `/scientific-writing` to write the scientific content, check citations, and ground claims in evidence. Write clear scientific Indonesian with a medical perspective; explain method choices. Flag missing facts instead of inventing results or references.

## Check

After editing, build the requested document once from the project root: `latexmk -xelatex -halt-on-error sempro.tex` or `latexmk -xelatex -halt-on-error buku-ta.tex`. If the target is unspecified and shared files changed, build both. If `latexmk` is unavailable, follow the README's `xelatex`/`biber` sequence. Report errors, PDF path, edits, and facts needing confirmation; check official requirements and supervisor guidance before submission.
