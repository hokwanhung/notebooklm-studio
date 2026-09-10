# notebooklm-studio

A [Google NotebookLM](https://notebooklm.google.com/) learning studio: **custom prompts** tuned for better reports, video overviews, audio podcasts, flashcards, and quizzes, plus the catalogs and exports that come out of those notebooks.

NotebookLM does the generation. This repo stores the prompt packs (shared and per-notebook), a bibliographic source list, and the artifacts you keep. It does not host books, replace NotebookLM, or cover only one subject.

Owner: [hokwanhung](https://github.com/hokwanhung).

## Prompts first

Default Studio/chat instructions live in [`prompts/`](prompts/), one pack per output type. Treat them as starting points: edit for the notebook, save overrides under `collections/<topic>/prompts/`, and keep what actually improved the result.

Any learning topic can be a collection. `collections/finance-and-investing/` is only the first example.

## Layout

Two axes:

- **Purpose prompts** in [`prompts/`](prompts/) — paste into any notebook.
- **Collections** in [`collections/`](collections/) — one NotebookLM notebook per topic.

```text
prompts/                         shared prompts by artifact type
templates/collection/            copy this to start a new topic
collections/
  finance-and-investing/         example notebook; add any learning topic
    sources/catalog.md           ISBN / title / author only
    prompts/                     collection-specific overrides
    outputs/
      reports/ video/ audio/ flashcards/ quizzes/
```

## How this maps to NotebookLM

1. Create a notebook in NotebookLM.
2. List allowed sources in `collections/<topic>/sources/catalog.md` (citations only).
3. Upload copies you are allowed to use **outside git** (your device or Google Drive).
4. Paste a prompt from `prompts/`, customize it, then keep a better version in the collection if needed.
5. Export artifacts and drop them into that collection’s `outputs/` folders.
6. Paste the notebook URL into `collections/<topic>/notebook.md`.
7. Commit. Optional: point NotebookLM at public Markdown URLs from this repo.

Details: [docs/workflow.md](docs/workflow.md).

## Formats

| Artifact | Commit as |
| --- | --- |
| Report | Markdown (preferred); optional PDF beside it in `outputs/reports/` |
| Audio podcast | MP3 (convert WAV before commit when you can) |
| Video | MP4 |
| Flashcards | Markdown plus Anki `.txt` or CSV |
| Quiz | Markdown plus CSV |

Audio, video, WAV, and PPTX are marked for [Git LFS](https://git-lfs.com/). Run `git lfs install` once on a machine before adding media.

## Intellectual property

This repo is **public**. Do not commit books or full-text extracts.

- Source catalogs are bibliographic: title, author, year, ISBN, why it belongs in the notebook.
- `.gitignore` blocks `.epub`, `.mobi`, `.azw3`, `.djvu`, and PDFs except generated reports under `collections/**/outputs/reports/`.
- NotebookLM outputs can quote sources. Keep quotes short. Outputs are not a substitute for the books.
- Upload into NotebookLM only copies you are allowed to use.

The MIT license covers prompts and scaffolding. Generated reports, media, flashcards, and quizzes may still be derivative of third-party works; do not treat them as freely reusable book text.

## Add a collection

```powershell
Copy-Item -Recurse templates\collection collections\your-topic-name
```

Then fill `README.md`, `notebook.md`, and `sources/catalog.md`. Customize prompts in that collection when the shared packs are not enough.

## Related

Public-page crawler used for NotebookLM-ready Markdown: [notebooklm-crawler](https://github.com/hokwanhung/notebooklm-crawler). It is a separate project; do not merge it here.
