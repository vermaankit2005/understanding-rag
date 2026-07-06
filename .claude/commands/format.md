---
description: Format the rough markdown cells in a notebook (grammar + clean markdown, voice preserved)
argument-hint: "@<notebook.ipynb>"
model: sonnet
---

Format the rough markdown cells in the notebook referenced below, directly in this session (do NOT spawn a subagent).

Target notebook: $ARGUMENTS

## Workflow

1. **Read** the notebook to get every cell and its `id`.
2. For each **markdown** cell, decide if it is already formatted:
   - Already formatted = its source begins with the marker `<!-- formatted -->`. **Skip these completely — never re-touch them.**
   - Unformatted = it does NOT start with that marker.
3. Rewrite each unformatted markdown cell (see rules) and save it with `NotebookEdit`, keeping the same `cell_id` and `cell_type: markdown`. Every formatted cell MUST begin with the exact first line `<!-- formatted -->` (an invisible marker that makes reruns idempotent).
4. **Ignore code cells and empty cells entirely.**
5. Report a short summary: which cell ids were formatted and which were skipped.

## What you MAY do

- Fix spelling, grammar, punctuation, spacing, capitalization.
- Improve sentence delivery so it reads smoothly (tighten run-ons, fix awkward phrasing).
- Add markdown structure where it genuinely helps: headings, **bold**/_italic_ emphasis, bullet/numbered lists when enumerating, inline `code` for technical terms/filenames/functions, blockquotes for asides.
- Add a simple mermaid/ASCII diagram when the text describes a flow or architecture.
- Turn bare URLs into proper markdown links with descriptive text.
- Emojis **very sparingly** — prefer none; at most one occasionally in a heading or closing line. Never on list items, never multiple per cell.

## What you must NOT do

- Do NOT change his ideas, opinions, or the order/flow of his thoughts. You are a copy-editor and typesetter, not a co-author.
- Do NOT add new facts or explanations he did not write. If something is technically wrong, leave it — this is his learning notebook.
- Do NOT remove personal, casual asides (e.g. "So here I am. Let's start RAG."). Keep his voice and first-person perspective.
- Do NOT touch code cells, outputs, or any cell already carrying the `<!-- formatted -->` marker.

## Style reference

The already-formatted intro cell is the tone target: personal, slightly informal, but clean. When in doubt, format less rather than rewriting more — preserving his voice always wins over polish.
