# Matrix products, powers, and orthogonality

This note adds the ideas used in 2023 Q4. For transpose and symmetric matrices, first read [Matrix adjoint, symmetry, and Hermitian matrices](matrix-adjoint-symmetry-and-hermitian.md#1-transpose-reflecting-entries-across-the-main-diagonal).

## 1. Matrix products and order

For a product \(C=AB\), each entry is found by multiplying a row of \(A\) by a column of \(B\):

> [!IMPORTANT]
> **Exam formula — matrix-product entry**
>
> \[
> (AB)_{ij}=\sum_k a_{ik}b_{kj}.
> \]

For example,

\[
\begin{pmatrix}a&b\\c&d\end{pmatrix}
\begin{pmatrix}e&f\\g&h\end{pmatrix}
=\begin{pmatrix}ae+bg&af+bh\\ce+dg&cf+dh\end{pmatrix}.
\]

The order usually matters: \(AB\) is not generally \(BA\). A particular pair is called **commutative** only when \(AB=BA\).

> [!IMPORTANT]
> **Exam formula — transpose reverses product order**
>
> \[
> (AB)^T=B^TA^T.
> \]

This reversal is exactly what connects the symmetry of \(AB\) to whether symmetric matrices \(A\) and \(B\) commute.

## 2. A fast matrix-power pattern

The identity matrix plays the role of \(1\): \(IA=AI=A\). If \(A=I+N\) and \(N^2=0\), then \(N\) is nonzero but disappears after it is multiplied by itself.

> [!IMPORTANT]
> **Exam formula — nilpotent shortcut**
>
> \[
> (I+N)^n=I+nN,\qquad n=0,1,2,\ldots,\quad N^2=0.
> \]

For example,

\[
(I+N)^2=I^2+IN+NI+N^2=I+N+N+0=I+2N.
\]

All terms with at least two \(N\)'s vanish. In an exam, prove the general statement by induction: multiply \(I+kN\) by \(I+N\), then use \(N^2=0\). This is the pattern in 2023 Q4(b).

## 3. Orthogonal matrices

A real square matrix is **orthogonal** when it preserves lengths and angles. Its columns are perpendicular unit vectors.

> [!IMPORTANT]
> **Exam test — orthogonal matrix**
>
> \[
> Q^TQ=I.
> \]

Consequently,

> [!IMPORTANT]
> **Exam result — inverse**
>
> \[
> Q^{-1}=Q^T.
> \]

For

\[
Q=\begin{pmatrix}\cos\alpha&\sin\alpha\\-\sin\alpha&\cos\alpha\end{pmatrix},
\]

the two columns have squared lengths \(\cos^2\alpha+\sin^2\alpha=1\), and their dot product is \(\cos\alpha\sin\alpha-\sin\alpha\cos\alpha=0\). So it represents a rotation, not a stretch. The formal proof calculates \(Q^TQ\).

## Quick recognition checklist

- “\(AB\) is symmetric” means transpose the product, reverse the order, and use \(A^T=A,\ B^T=B\).
- If a power matrix has diagonal entries near \(1\), calculate \(N=A-I\), then test whether \(N^2=0\).
- “Orthogonal” means calculate \(A^T A\) and obtain \(I\).
