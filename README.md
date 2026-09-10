# notebooklm-studio

Versioned archive next to [Google NotebookLM](https://notebooklm.google.com/): reusable prompts, bibliographic source catalogs, and exported artifacts (reports, video, audio podcasts, flashcards, quizzes).

NotebookLM stays the generation tool. This repository does not host books, does not replace NotebookLM, and is not a product integration.

Owner: [hokwanhung](https://github.com/hokwanhung).

Finance and investing is the first collection, not the whole studio. Add a folder under `collections/` whenever a topic has its own NotebookLM notebook.

## Suggested collections

Pick topics with a **bounded source set** (a shelf of books, a paper pack, or public reports) that you want to turn into a report, video, podcast, flashcards, and quiz. Copy `templates/collection` when you start one.

| Folder | Good for | Typical sources (catalog only in git) |
| --- | --- | --- |
| `finance-and-investing` | Markets, allocation, investor behavior | Books you own; skip the files |
| `economics` | Micro/macro, trade-offs, institutions | Textbooks, classic papers, public data notes |
| `business-and-strategy` | Firms, competition, operating cadence | Strategy and management books |
| `decision-making` | Judgment, uncertainty, mental models | Decision-science and psychology books |
| `career-and-management` | Teams, hiring, communication at work | Management books, public essays |
| `writing-and-rhetoric` | Clear prose, argument, editing | Style manuals, rhetoric books |
| `history` | Periods, debates, primary vs secondary | Histories and document collections you may use |
| `science-literacy` | Mechanisms, evidence, limits of studies | Popular science plus papers you can access |
| `software-and-systems` | Architecture, reliability, practice | Books and public RFCs/docs (not private code) |
| `public-policy` | Institutions, regulation, civic tech | White papers, statutes, official reports |
| `security-and-privacy` | Threat models, defensive practice | Public standards and books you own |

Skip a topic if you cannot list sources you are allowed to upload. Do not create empty folders until you actually open the notebook.

## Layout

Two axes:

- **Purpose prompts** in [`prompts/`](prompts/) — paste into any notebook.
- **Collections** in [`collections/`](collections/) — one NotebookLM notebook per topic.

```text
prompts/                         shared prompts by artifact type
templates/collection/            copy this to start a new topic
collections/
  finance-and-investing/         first notebook; more topics later
    sources/catalog.md           ISBN / title / author only
    prompts/                     collection-specific overrides
    outputs/
      reports/ video/ audio/ flashcards/ quizzes/
```

## How this maps to NotebookLM

1. Create a notebook in NotebookLM.
2. List allowed sources in `collections/<topic>/sources/catalog.md` (citations only).
3. Upload copies you are allowed to use **outside git** (your device or Google Drive).
4. Run prompts from `prompts/` (or the collection `prompts/` overrides).
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

Then fill `README.md`, `notebook.md`, and `sources/catalog.md`. Add collection-specific prompts only when the shared packs are not enough.

## Related

Public-page crawler used for NotebookLM-ready Markdown: [notebooklm-crawler](https://github.com/hokwanhung/notebooklm-crawler). It is a separate project; do not merge it here.
