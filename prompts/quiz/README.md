# Quiz prompts

Paste [`prompt.md`](prompt.md) when generating a quiz.

## Expected files

Put exports in `collections/<topic>/outputs/quizzes/`:

- `<slug>.md` — questions, choices, correct answer, short explanation
- `<slug>.csv` — columns `question,a,b,c,d,correct,explanation,source`

If NotebookLM only gives a share link, copy the items into these files before you close the session.
