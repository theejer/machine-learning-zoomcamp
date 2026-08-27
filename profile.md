# machine-learning-zoomcamp — Learner Profile

Why this course matters:

## Concepts
| Concept | Mastery | Last reviewed | Lesson | Notes |
|---|---|---|---|---|
| Matrix-vector multiplication dimension rule | shaky | 2026-08-27 | | Initially read `U.shape[1] == v.shape[0]` as a different/new rule from `u.shape[0] == v.shape[0]` in vector-vector multiplication; didn't immediately see that `U.shape[1]` is just "the length of a row of U" and the underlying dot-product-equal-length rule is unchanged. |
| Matrix-matrix multiplication implementation | shaky | 2026-08-27 | | In a draft `matrix_matrix_multiplication`, asserted both `U.shape[0]==V.shape[1]` AND `U.shape[1]==V.shape[0]` (over-constrained; only the inner-dimension check is needed), and looped over rows of U while indexing `V[i,:]` (a row) instead of looping over columns of V and indexing `V[:,i]` — same row-vs-column axis mix-up as the matrix-vector case, one level up. Result array shape was also wrong (`(U.shape[0], U.shape[1])` instead of `(U.shape[0], V.shape[1])`). |
