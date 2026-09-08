# Math 1227 — 2022 Q4 study guide

All three parts are already fully covered in the cumulative matrix library:

## Q4(a) Symmetric and skew-Hermitian matrices

> Define symmetric and skew-Hermitian matrix with example.

Read [Matrix adjoint, symmetry, and Hermitian matrices](../concepts/matrix-adjoint-symmetry-and-hermitian.md#2-symmetric-and-skew-symmetric-parts) for symmetric matrices, then [conjugate transpose and Hermitian matrices](../concepts/matrix-adjoint-symmetry-and-hermitian.md#4-complex-conjugate-conjugate-transpose-and-hermitian-part). A skew-Hermitian matrix satisfies \(K^\dagger=-K\); it is the complex-number analogue of a real skew-symmetric matrix.

## Q4(b) Unique symmetric and skew-symmetric decomposition

> Show that every square matrix can be uniquely expressed as the sum of a symmetric and skew-symmetric matrices.

Use the highlighted decomposition formulas in [symmetric and skew-symmetric parts](../concepts/matrix-adjoint-symmetry-and-hermitian.md#2-symmetric-and-skew-symmetric-parts):

\[
S=\frac{A+A^T}{2},\qquad K=\frac{A-A^T}{2}.
\]

They give \(A=S+K\), \(S^T=S\), and \(K^T=-K\). For uniqueness, if \(A=S_1+K_1=S_2+K_2\), then \(S_1-S_2=K_2-K_1\). The left side is symmetric and the right side skew-symmetric; a matrix that is both must be zero. Hence \(S_1=S_2\) and \(K_1=K_2\).

## Q4(c) Rank and normal form

> Define rank of a matrix. Reduce the given matrix into normal form and hence find its rank.

This is exactly the same matrix and calculation as [2024 Q6(a)](../2024/q6-study-guide.md#q6a-rank-and-normal-form). Read that complete worked solution; its normal form has three pivots, so the rank is \(3\).
