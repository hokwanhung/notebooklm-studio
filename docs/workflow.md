# NotebookLM workflow

Work in NotebookLM. Keep custom prompts and exports here. Do not put books in git.

Start from [`prompts/report.md`](../prompts/report.md). Use another file in `prompts/` only when you generate that Studio type.

## 1. Collection

Copy `templates/collection` to `collections/<topic>/` and name the folder in kebab-case.

Fill:

- `README.md` — categories and reading order
- `notebook.md` — NotebookLM URL(s) after you create them
- `sources/catalog.md` — bibliographic rows only

## 2. NotebookLM notebook

1. Create a notebook at [notebooklm.google.com](https://notebooklm.google.com/).
2. Add sources from copies you are allowed to use. Put those files in `local/<topic>/<category>/` (gitignored). Never commit books to this repo.
3. Paste the notebook link into `notebook.md`.

## 3. Prompts

Paste [`prompts/report.md`](../prompts/report.md) into Reports (or chat). Open another file only when you generate that type:

| Studio type | File |
| --- | --- |
| Report | [`prompts/report.md`](../prompts/report.md) |
| Video | [`prompts/video.md`](../prompts/video.md) — pick **Explainer**, landscape 16:9, not Short or Cinematic |
| Audio | [`prompts/audio-podcast.md`](../prompts/audio-podcast.md) |
| Flashcards | [`prompts/flashcards.md`](../prompts/flashcards.md) |
| Quiz | [`prompts/quiz.md`](../prompts/quiz.md) |

## 4. Export

NotebookLM’s native export is limited (Google Docs/Sheets, WAV audio, video download; flashcards and quizzes are often share links). Convert before commit:

| Artifact | Preferred files |
| --- | --- |
| Report | `outputs/<slug>.md` and optional `<slug>.pdf` |
| Video | `outputs/<slug>.mp4` plus a short `.md` notes file |
| Audio | `outputs/<slug>.mp3` (convert WAV → MP3 when possible) |
| Flashcards | `outputs/<slug>.md` and `<slug>.csv` or Anki `.txt` |
| Quiz | `outputs/<slug>.md` and `<slug>.csv` |

Suggested slug: `YYYY-MM-DD-short-title`.

Keep quotes short. Do not dump a book into a report.

## 5. Commit

```powershell
git add collections/<topic>
git status   # confirm no .epub / .mobi / source PDFs
```

Media (`.mp3`, `.mp4`, `.wav`, `.pptx`) uses Git LFS via `.gitattributes`. On a new machine:

```powershell
git lfs install
```

Then commit and push as usual.

## 6. Optional loop

Public Markdown from this repo can be added back to NotebookLM as a URL source if you want later notebooks to build on earlier reports.
