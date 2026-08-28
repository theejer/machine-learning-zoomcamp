# Machine Learning Zoomcamp — Learner Profile

Why this course matters:

## Concepts
| Concept | Mastery | Last reviewed | Lesson | Notes |
|---|---|---|---|---|
| Pandas — counting rows vs. per-column non-null counts | shaky | 2026-08-28 | | HW1 Q2: used `df.count()` (per-column non-null) to answer "how many records" instead of `len(df)`/`df.shape[0]`; got the right number only because the columns checked happened to have no nulls |
| Pandas — counting distinct categorical values | shaky | 2026-08-28 | | HW1 Q3: used `groupby(...).mean()` and eyeballed the row count to answer "how many fuel types" instead of `.nunique()`; right answer, wrong tool |
| Pandas — fillna + recomputing summary stats | untested | 2026-08-28 | | HW1 Q6 left incomplete — computed median before fillna (149.0) but never found the mode, applied fillna, or recomputed the median after |
| NumPy — normal equation (XTX inverse, linear regression by hand) | solid | 2026-08-28 | | HW1 Q7 done correctly end-to-end: build X, XTX, invert, multiply by y, matches reference (0.5188 → 0.51) |
