# Video prompts

Paste [`prompt.md`](prompt.md) into the Video Overview custom instruction, then set Studio options to match it.

## Length: one Explainer, not a stack of Shorts

NotebookLM length is mostly the **format**, not how terse the prompt is.

| Studio format | Typical result | Use |
| --- | --- | --- |
| **Explainer** | Landscape 16:9, a few minutes, structured walkthrough | Default for this pack |
| Short | Vertical 9:16, ~60 seconds, one idea | Phone clip only; skip unless you want that |
| Cinematic | Animated / immersive | Conflicts with the pack (labels and diagrams, not B-roll) |

If a run came out at about a minute, you almost certainly generated **Short** (or an older **Brief**). Do not fix that by making several Shorts. Generate one Explainer for the notebook.

Split into a second video only when the notebook is too broad for one pass (for example one book, or one named framework). Use Studio’s topic / steering field to name that slice. Keep Shorts as optional extras after the Explainer, not the main artifact.

## Orientation

Always choose **landscape / 16:9 / horizontal** if the UI offers an aspect ratio. Short is portrait by design; do not use it when you want a desk-watchable explainer.

The pack is a single-narrator explainer: labeled beats, simple graphics, humor only when a source distinction is already funny. It is in the spirit of a CGP Grey video, not an impersonation — do not copy his scripts, catchphrases, or voice. For a two-host conversation, use the audio pack instead.

## Expected files

Put exports in `collections/<topic>/outputs/video/`:

- `<slug>.mp4` — video download
- `<slug>.md` — title, length, date, one-paragraph summary, notebook link

Git LFS tracks `*.mp4` and `*.pptx`.
