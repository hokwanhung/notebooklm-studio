# Audio podcast prompts

Paste [`prompt.md`](prompt.md) into Audio Overview custom instructions.

## Expected files

Put exports in `collections/<topic>/outputs/audio/`:

- `<slug>.mp3` — preferred (convert NotebookLM WAV first)
- `<slug>.wav` — only if you cannot convert; Git LFS tracks WAV
- `<slug>.md` — title, duration, hosts/format (Deep Dive, Brief, Critique, Debate), date, summary

Prefer MP3 in git; WAV files are large.
