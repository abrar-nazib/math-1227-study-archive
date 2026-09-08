# Math 1227 — 2022 Q4 study guide

All three parts are already fully covered in the cumulative matrix library:

## Q4(a) Symmetric and skew-Hermitian matrices

> Define symmetric and skew-Hermitian matrix with example.

A real square matrix \(S\) is symmetric when \(S^T=S\). For example,

\[
\begin{pmatrix}2&3\\3&1\end{pmatrix}^T
=\begin{pmatrix}2&3\\3&1\end{pmatrix}.
\]

For a complex matrix, \(K^\dagger=(\overline K)^T\). A matrix is skew-Hermitian when

\[
K^\dagger=-K.
\]

For example,

\[
K=\begin{pmatrix}i&1+i\\-1+i&-2i\end{pmatrix}.
\]

\[
\overline K=\begin{pmatrix}-i&1-i\\-1-i&2i\end{pmatrix}.
\]

\[
K^\dagger=\begin{pmatrix}-i&-1-i\\1-i&2i\end{pmatrix}=-K.
\]

## Q4(b) Unique symmetric and skew-symmetric decomposition

> Show that every square matrix can be uniquely expressed as the sum of a symmetric and skew-symmetric matrices.

Let \(A\) be any real square matrix. Define

\[
S=\frac{A+A^T}{2},\qquad K=\frac{A-A^T}{2}.
\]

\[
S=\frac{A+A^T}{2},\qquad K=\frac{A-A^T}{2}.
\]

\[
S+K=\frac{A+A^T+A-A^T}{2}=A.
\]

\[
S^T=\left(\frac{A+A^T}{2}\right)^T=\frac{A^T+(A^T)^T}{2}=\frac{A^T+A}{2}=S.
\]

\[
K^T=\left(\frac{A-A^T}{2}\right)^T=\frac{A^T-A}{2}=-\frac{A-A^T}{2}=-K.
\]

Thus \(A=S+K\), with \(S\) symmetric and \(K\) skew-symmetric.

For uniqueness, suppose

\[
A=S_1+K_1=S_2+K_2,
\]

where both \(S_1,S_2\) are symmetric and both \(K_1,K_2\) are skew-symmetric. Then

\[
S_1-S_2=K_2-K_1.
\]

The left side is symmetric; the right side is skew-symmetric. A matrix \(D\) that is both satisfies \(D^T=D\) and \(D^T=-D\), so \(D=-D\), hence \(D=0\). Therefore

\[
S_1-S_2=0,\qquad K_2-K_1=0,
\]

\[
\boxed{S_1=S_2,\qquad K_1=K_2.}
\]

## Q4(c) Rank and normal form

> Define rank of a matrix. Reduce the given matrix into normal form and hence find its rank.

Let

\[
A=\begin{pmatrix}2&3&-1&-1\\1&-1&-2&-4\\3&1&3&-2\\6&3&0&-7\end{pmatrix}.
\]

Interchange \(R_1,R_2\), then eliminate below the first pivot:

\[
\begin{pmatrix}1&-1&-2&-4\\0&5&3&7\\0&4&9&10\\0&9&12&17\end{pmatrix}.
\]

\[
R_3\to5R_3-4R_2=(0,0,33,22),\qquad
R_4\to5R_4-9R_2=(0,0,33,22).
\]

\[
R_4\to R_4-R_3=(0,0,0,0).
\]

Thus the echelon form is

\[
\begin{pmatrix}1&-1&-2&-4\\0&5&3&7\\0&0&33&22\\0&0&0&0\end{pmatrix}.
\]

Scale pivots and clear above them:

\[
\begin{pmatrix}1&0&0&-\frac53\\0&1&0&1\\0&0&1&\frac23\\0&0&0&0\end{pmatrix}.
\]

Finally use

\[
C_4\to C_4+\frac53C_1-C_2-\frac23C_3,
\]

giving

\[
\boxed{\begin{pmatrix}1&0&0&0\\0&1&0&0\\0&0&1&0\\0&0&0&0\end{pmatrix}}.
\]

There are three nonzero rows, so

\[
\boxed{\operatorname{rank}(A)=3.}
\]
