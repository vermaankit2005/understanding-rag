# RAG from Scratch — Project Notes

A personal, learning-focused reimplementation of RAG concepts across Jupyter notebooks. The markdown is written rough by the author and polished with the `/format` command.

## House rules (default to token-cheap behavior)

- **Model:** Prefer Sonnet for mechanical work (formatting, renaming, boilerplate, simple edits). Reserve Opus for real reasoning/design. The `/format` command already pins `model: sonnet`.
- **Don't re-read whole notebooks.** When only one cell changed, work from the cell id / snippet given — do not re-Read the entire `.ipynb`.
- **Prefer commands over subagents** for small, well-defined, repeatable tasks. Only spin a subagent when isolation (keeping big/noisy output out of context) or backgrounding is the actual goal.
- **Targeted search, not broad exploration,** when the location is already known (Grep a path beats "figure out how X works").
- **Keep huge output out of context** — pipe long logs/command output to a file or `head` it instead of dumping it all.
- **Ask before large multi-file rewrites**; batch requirements up front rather than drip-feeding corrections.

## Formatting the notebooks

- Run `/format @<notebook.ipynb>` to polish rough markdown cells.
- Cells already carrying the `<!-- formatted -->` marker are skipped (idempotent).
- Formatting fixes grammar/delivery and adds clean markdown structure **without** changing the author's ideas, order, or personal voice. Emojis are used very sparingly.
