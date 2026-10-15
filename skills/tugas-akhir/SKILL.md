---
name: tugas-akhir
description: Create a Medical Technology ITS thesis project in the user's workspace, help write its content, or check proposal and thesis PDFs.
---

# Medical Technology ITS thesis

Work in the user's current workspace. The adjacent `template/` directory contains the full project sources. Resolve it relative to this installed SKILL.md file, not the source repository or an internet URL.

## Start a project

Inspect the workspace first. If it already contains a thesis project, work with that project and ask what the user wants done; do not copy the template again. Otherwise, offer to copy the template. Show the destination and obtain consent before copying. Copy the contents into an empty destination with `cp -a <installed-skill-directory>/template/. <workspace>/`. If the workspace contains other files, ask the user to choose a new empty subdirectory; never overwrite files or merge projects automatically. Confirm that `sempro.tex`, `buku-ta.tex`, `bab/`, and `pustaka/variables.tex` exist at the destination.

## Write

Ask which section needs work and what study data and sources are available. Identity, title, and supervisors belong in `pustaka/variables.tex`; abstracts in `abstrak/`; chapters in `bab/`; references in `pustaka/pustaka.bib`. Chapters 1–3 are shared by proposal and thesis. Write from the user's data and sources, using a medical perspective and clear scientific Indonesian; explain why a method was chosen. Mark missing study details for confirmation instead of inventing results, numbers, or references. After completing the requested edits, run the Check step once for the user's target document; if the target is unspecified and shared files changed, build both documents. Report the build result and PDF path, then show edits for user review. Do not rebuild after each individual file edit.

## Check

From the project root, build `sempro.tex` for the proposal or `buku-ta.tex` for the thesis with `latexmk -pdf -halt-on-error <filename>.tex` when available. Otherwise, run `pdflatex`, `biber`, then `pdflatex` twice as described in the repository README. Report compilation errors and the PDF path. A successful build does not validate scientific claims; check official department requirements and supervisor guidance before submission.
