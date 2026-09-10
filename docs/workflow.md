# NotebookLM workflow

Create in NotebookLM, archive here. Do not put books in git.

## 1. Collection

Copy `templates/collection` to `collections/<topic>/` and name the folder in kebab-case.

Fill:

- `README.md` — what the notebook is for
- `notebook.md` — NotebookLM URL after you create it
- `sources/catalog.md` — bibliographic rows only (title, author, year, ISBN, notes)

## 2. NotebookLM notebook

1. Create a notebook at [notebooklm.google.com](https://notebooklm.google.com/).
2. Add sources from copies you are allowed to use (local files, Drive, or allowed URLs). Never commit those files to this repo.
3. Paste the notebook link into `notebook.md`.

## 3. Prompts

Paste a pack from `prompts/` into chat or a custom Studio instruction:

| Goal | File |
| --- | --- |
| Report | [`prompts/report/prompt.md`](../prompts/report/prompt.md) |
| Video | [`prompts/video/prompt.md`](../prompts/video/prompt.md) |
| Audio podcast | [`prompts/audio-podcast/prompt.md`](../prompts/audio-podcast/prompt.md) |
| Flashcards | [`prompts/flashcards/prompt.md`](../prompts/flashcards/prompt.md) |
| Quiz | [`prompts/quiz/prompt.md`](../prompts/quiz/prompt.md) |

If the topic needs different wording, put an override in `collections/<topic>/prompts/` and say so in that folder’s README.

## 4. Export

NotebookLM’s native export is limited (Google Docs/Sheets, WAV audio, video download; flashcards and quizzes are often share links). Convert before commit:

| Artifact | Preferred files |
| --- | --- |
| Report | `outputs/reports/<slug>.md` and optional `<slug>.pdf` |
| Video | `outputs/video/<slug>.mp4` plus a short `README` or `.md` notes file |
| Audio | `outputs/audio/<slug>.mp3` (convert WAV → MP3 when possible) |
| Flashcards | `outputs/flashcards/<slug>.md` and `<slug>.csv` or Anki `.txt` |
| Quiz | `outputs/quizzes/<slug>.md` and `<slug>.csv` |

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
