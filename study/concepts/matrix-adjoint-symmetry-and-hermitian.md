# Matrix adjoint, symmetry, and Hermitian matrices

This note is the small matrix toolkit needed for 2024 Q4. A matrix is a rectangular arrangement of numbers. Its entry in row \(i\), column \(j\) is written \(a_{ij}\). Q4 uses square matrices: the same number of rows and columns.

## 1. Transpose: reflecting entries across the main diagonal

The **transpose** of \(A\), written \(A^T\), exchanges every row with the matching column:

\[
(A^T)_{ij}=a_{ji}.
\]

Imagine the main diagonal as a mirror. An entry one place to the right of the diagonal moves to the matching place below it. Diagonal entries do not move.

For example,

\[
A=\begin{pmatrix}a&b\\c&d\end{pmatrix}
\quad\Longrightarrow\quad
A^T=\begin{pmatrix}a&c\\b&d\end{pmatrix}.
\]

> [!IMPORTANT]
> **Exam formula — transpose twice returns the original matrix**
>
> \[
> (A^T)^T=A.
> \]

## 2. Symmetric and skew-symmetric parts

A real square matrix is **symmetric** when its mirror image is unchanged: \(A^T=A\). It is **skew-symmetric** when transposing reverses every sign: \(A^T=-A\). In particular, every diagonal entry of a skew-symmetric matrix is \(0\), because \(k=-k\) only when \(k=0\).

Any real square matrix can be separated into a mirror-preserving part and a sign-reversing part. The two pieces add back to the original matrix.

> [!IMPORTANT]
> **Exam formulas — symmetric and skew-symmetric decomposition**
>
> \[
> S=\frac{A+A^T}{2},\qquad K=\frac{A-A^T}{2},\qquad A=S+K.
> \]
>
> Here \(S^T=S\), and \(K^T=-K\).

The addition \(A+A^T\) pairs each entry with its reflected partner and makes both positions agree. The subtraction \(A-A^T\) makes reflected partners opposite. Dividing by \(2\) prevents the pieces from being counted twice.

## 3. Minor, cofactor, and adjoint (adjugate)

For a square matrix \(A\), the **minor** \(M_{ij}\) is the determinant left after deleting row \(i\) and column \(j\). The corresponding **cofactor** includes an alternating sign:

> [!IMPORTANT]
> **Exam formulas — minor and cofactor**
>
> \[
> C_{ij}=(-1)^{i+j}M_{ij}.
> \]

For a \(2\times2\) matrix, this is especially visible:

\[
A=\begin{pmatrix}a&b\\c&d\end{pmatrix}.
\]

Deleting the row and column of each entry gives

\[
M_{11}=d,\quad M_{12}=c,\quad M_{21}=b,\quad M_{22}=a.
\]

Thus the cofactor matrix is

\[
C=\begin{pmatrix}d&-c\\-b&a\end{pmatrix}.
\]

The **adjoint** in this question means the **adjugate**: transpose the cofactor matrix. (This is different from the conjugate transpose, which is also sometimes called an adjoint in complex-matrix contexts.)

> [!IMPORTANT]
> **Exam formula — adjoint / adjugate**
>
> \[
> \operatorname{adj}(A)=C^T,
> \]
>
> where \(C=(C_{ij})\) is the cofactor matrix of \(A\).

For the \(2\times2\) example,

\[
\operatorname{adj}(A)=\begin{pmatrix}d&-b\\-c&a\end{pmatrix}.
\]

### Why symmetric matrices have symmetric adjoints

If \(A=A^T\), entry \(a_{ij}\) matches \(a_{ji}\). After deleting row \(i\), column \(j\), the remaining matrix is the transpose of the matrix obtained by deleting row \(j\), column \(i\). A determinant is unchanged by transpose, so

\[
M_{ij}=M_{ji}.
\]

The cofactor signs also match because \(i+j=j+i\). Therefore \(C_{ij}=C_{ji}\): the cofactor matrix is symmetric. Its transpose, \(\operatorname{adj}(A)\), is consequently symmetric too.

## 4. Complex conjugate, conjugate transpose, and Hermitian part

For a complex number, the **conjugate** changes the sign of \(i\):

\[
\overline{a+bi}=a-bi.
\]

For a complex matrix \(A\), first conjugate every entry to get \(\overline A\), then transpose. This is the **conjugate transpose**, written \(A^\dagger\):

> [!IMPORTANT]
> **Exam formula — conjugate transpose**
>
> \[
> A^\dagger=(\overline A)^T.
> \]

A complex matrix is **Hermitian** if \(H^\dagger=H\). It is the complex version of a symmetric matrix: entries reflected across the main diagonal are conjugates, rather than necessarily identical. Its diagonal entries must be real.

> [!IMPORTANT]
> **Exam formula — Hermitian part of a complex matrix**
>
> \[
> H=\frac{A+A^\dagger}{2}.
> \]

The average pairs each entry with the conjugate of its reflected partner. That makes the result Hermitian. On the diagonal, \((z+\overline z)/2\) keeps only the real part, so no imaginary diagonal entry remains.

## Quick recognition checklist

- The words “symmetric and skew symmetric part” mean: calculate \(A^T\), then use \(\frac{A+A^T}{2}\) and \(\frac{A-A^T}{2}\).
- The word “adjoint” alongside minors/cofactors or a symmetric-matrix proof means \(\operatorname{adj}(A)=C^T\), not conjugate transpose.
- The word “Hermitian” means: calculate \(A^\dagger\), not merely \(A^T\), then average \(A\) and \(A^\dagger\).
