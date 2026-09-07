# Math 1227 — 2024 Q4 study guide

Q4 is a matrix question. Read [Matrix adjoint, symmetry, and Hermitian matrices](../concepts/matrix-adjoint-symmetry-and-hermitian.md) first; it contains the reusable definitions and exam formulas used below.

## Q4(a) Adjoint of a symmetric matrix

> What is the adjoint of a matrix? Prove that the adjoint of a symmetric matrix is itself symmetric.

### Underlying-concept map

1. A **minor** is a determinant obtained after deleting one row and one column.
2. A **cofactor** is its minor with the sign \((-1)^{i+j}\).
3. The adjoint (also called adjugate here) is the transpose of the cofactor matrix.
4. A symmetric matrix has matching entries across its main diagonal. That matching makes the matching minors, then cofactors, equal.

### Solve it yourself

1. Define the cofactor matrix \(C=(C_{ij})\), and state how \(\operatorname{adj}(A)\) is made from it.
2. Start with \(A=A^T\). Compare the minor after deleting row \(i\), column \(j\) with the minor after deleting row \(j\), column \(i\).
3. Include the cofactor sign and show \(C_{ij}=C_{ji}\).
4. Use \(\operatorname{adj}(A)=C^T\) to finish.

### Detailed answer

Let \(M_{ij}\) denote the minor of the entry \(a_{ij}\). Thus \(M_{ij}\) is the determinant of the matrix remaining after row \(i\) and column \(j\) are deleted.

The cofactor of \(a_{ij}\) is

\[
C_{ij}=(-1)^{i+j}M_{ij}.
\]

If \(C=(C_{ij})\) is the cofactor matrix, then the **adjoint** (adjugate) of \(A\) is

\[
\operatorname{adj}(A)=C^T.
\]

Now suppose \(A\) is symmetric. By definition,

\[
A=A^T.
\]

Therefore every reflected pair of entries is equal:

\[
a_{ij}=a_{ji}.
\]

Delete row \(i\) and column \(j\) of \(A\). Because \(A=A^T\), the remaining matrix is the transpose of the matrix obtained by deleting row \(j\) and column \(i\). A determinant is unchanged by transpose, so

\[
M_{ij}=M_{ji}.
\]

Now compare the two cofactors:

\[
C_{ij}=(-1)^{i+j}M_{ij},
\]

\[
C_{ji}=(-1)^{j+i}M_{ji}.
\]

Since \(j+i=i+j\),

\[
(-1)^{j+i}=(-1)^{i+j}.
\]

Since \(M_{ji}=M_{ij}\),

\[
C_{ji}=(-1)^{i+j}M_{ij}.
\]

Hence

\[
C_{ji}=C_{ij}.
\]

So the cofactor matrix is symmetric:

\[
C^T=C.
\]

Finally,

\[
\operatorname{adj}(A)=C^T=C.
\]

Taking the transpose once more gives

\[
\bigl(\operatorname{adj}(A)\bigr)^T=C^T.
\]

But \(C^T=C=\operatorname{adj}(A)\). Therefore

\[
\boxed{\bigl(\operatorname{adj}(A)\bigr)^T=\operatorname{adj}(A).}
\]

Thus the adjoint of a symmetric matrix is itself symmetric.

## Q4(b) Symmetric and skew-symmetric parts

> Find the symmetric and skew symmetric part of \(A=\begin{pmatrix}2&3&4\\4&3&1\\1&2&4\end{pmatrix}\).

### Underlying-concept map

1. Transpose \(A\) by exchanging its rows and columns.
2. The symmetric part is \((A+A^T)/2\).
3. The skew-symmetric part is \((A-A^T)/2\).
4. Check that the first result equals its transpose, the second changes sign when transposed, and their sum is \(A\).

### Solve it yourself

1. Write \(A^T\) carefully. In particular, the second column of \(A\) becomes the second row of \(A^T\).
2. Add \(A\) and \(A^T\) entry by entry, then divide every entry by \(2\).
3. Subtract \(A^T\) from \(A\) entry by entry, then divide every entry by \(2\).
4. Check the off-diagonal positions across the main diagonal.

### Detailed answer

Given

\[
A=\begin{pmatrix}
2&3&4\\
4&3&1\\
1&2&4
\end{pmatrix},
\]

its transpose is obtained by turning columns into rows:

\[
A^T=\begin{pmatrix}
2&4&1\\
3&3&2\\
4&1&4
\end{pmatrix}.
\]

The symmetric part is

\[
S=\frac{A+A^T}{2}.
\]

First add the matrices entry by entry:

\[
A+A^T
=\begin{pmatrix}
2&3&4\\
4&3&1\\
1&2&4
\end{pmatrix}
+\begin{pmatrix}
2&4&1\\
3&3&2\\
4&1&4
\end{pmatrix}
\]

\[
=\begin{pmatrix}
2+2&3+4&4+1\\
4+3&3+3&1+2\\
1+4&2+1&4+4
\end{pmatrix}
\]

\[
=\begin{pmatrix}
4&7&5\\
7&6&3\\
5&3&8
\end{pmatrix}.
\]

Now divide every entry by \(2\):

\[
S=\frac12\begin{pmatrix}
4&7&5\\
7&6&3\\
5&3&8
\end{pmatrix}
\]

\[
=\begin{pmatrix}
4/2&7/2&5/2\\
7/2&6/2&3/2\\
5/2&3/2&8/2
\end{pmatrix}
\]

\[
=\boxed{\begin{pmatrix}
2&\frac72&\frac52\\
\frac72&3&\frac32\\
\frac52&\frac32&4
\end{pmatrix}}.
\]

The skew-symmetric part is

\[
K=\frac{A-A^T}{2}.
\]

First subtract entry by entry:

\[
A-A^T
=\begin{pmatrix}
2&3&4\\
4&3&1\\
1&2&4
\end{pmatrix}
-\begin{pmatrix}
2&4&1\\
3&3&2\\
4&1&4
\end{pmatrix}
\]

\[
=\begin{pmatrix}
2-2&3-4&4-1\\
4-3&3-3&1-2\\
1-4&2-1&4-4
\end{pmatrix}
\]

\[
=\begin{pmatrix}
0&-1&3\\
1&0&-1\\
-3&1&0
\end{pmatrix}.
\]

Now divide every entry by \(2\):

\[
K=\frac12\begin{pmatrix}
0&-1&3\\
1&0&-1\\
-3&1&0
\end{pmatrix}
\]

\[
=\begin{pmatrix}
0/2&-1/2&3/2\\
1/2&0/2&-1/2\\
-3/2&1/2&0/2
\end{pmatrix}
\]

\[
=\boxed{\begin{pmatrix}
0&-\frac12&\frac32\\
\frac12&0&-\frac12\\
-\frac32&\frac12&0
\end{pmatrix}}.
\]

Check the two properties. The reflected entries of \(S\) match, so \(S^T=S\). The reflected entries of \(K\) have opposite signs and its diagonal is zero, so \(K^T=-K\).

Finally, add the two parts:

\[
S+K
=\begin{pmatrix}
2&\frac72&\frac52\\
\frac72&3&\frac32\\
\frac52&\frac32&4
\end{pmatrix}
+\begin{pmatrix}
0&-\frac12&\frac32\\
\frac12&0&-\frac12\\
-\frac32&\frac12&0
\end{pmatrix}
\]

\[
=\begin{pmatrix}
2&\frac72-\frac12&\frac52+\frac32\\
\frac72+\frac12&3&\frac32-\frac12\\
\frac52-\frac32&\frac32+\frac12&4
\end{pmatrix}
\]

\[
=\begin{pmatrix}
2&3&4\\
4&3&1\\
1&2&4
\end{pmatrix}=A.
\]

## Q4(c) Hermitian part

> Find the Hermitian part of \(A=\begin{pmatrix}2+3i&1-i&2+i\\3&4+3i&5\\1&1+i&2i\end{pmatrix}\).

### Underlying-concept map

1. Conjugating a complex number reverses the sign of its imaginary part.
2. The conjugate transpose \(A^\dagger\) means conjugate every entry, then transpose.
3. The Hermitian part is \((A+A^\dagger)/2\), the complex-matrix counterpart of the symmetric part.
4. Check that entries reflected across the diagonal are conjugates and that diagonal entries are real.

### Solve it yourself

1. Form \(\overline A\), changing \(i\) to \(-i\) in every imaginary term.
2. Transpose \(\overline A\) to obtain \(A^\dagger\).
3. Add \(A\) and \(A^\dagger\) entry by entry, then divide by \(2\).
4. Inspect one reflected pair, such as positions \((1,2)\) and \((2,1)\), and the diagonal.

### Detailed answer

Given

\[
A=\begin{pmatrix}
2+3i&1-i&2+i\\
3&4+3i&5\\
1&1+i&2i
\end{pmatrix},
\]

the Hermitian part is

\[
H=\frac{A+A^\dagger}{2},
\]

where

\[
A^\dagger=(\overline A)^T.
\]

First conjugate every entry of \(A\). The real entries \(3\), \(5\), and \(1\) are unchanged:

\[
\overline A=\begin{pmatrix}
\overline{2+3i}&\overline{1-i}&\overline{2+i}\\
\overline3&\overline{4+3i}&\overline5\\
\overline1&\overline{1+i}&\overline{2i}
\end{pmatrix}
\]

\[
=\begin{pmatrix}
2-3i&1+i&2-i\\
3&4-3i&5\\
1&1-i&-2i
\end{pmatrix}.
\]

Now transpose this matrix:

\[
A^\dagger=(\overline A)^T
\]

\[
=\begin{pmatrix}
2-3i&3&1\\
1+i&4-3i&1-i\\
2-i&5&-2i
\end{pmatrix}.
\]

Add \(A\) and \(A^\dagger\) entry by entry:

\[
A+A^\dagger
=\begin{pmatrix}
2+3i&1-i&2+i\\
3&4+3i&5\\
1&1+i&2i
\end{pmatrix}
+\begin{pmatrix}
2-3i&3&1\\
1+i&4-3i&1-i\\
2-i&5&-2i
\end{pmatrix}
\]

\[
=\begin{pmatrix}
(2+3i)+(2-3i)&(1-i)+3&(2+i)+1\\
3+(1+i)&(4+3i)+(4-3i)&5+(1-i)\\
1+(2-i)&(1+i)+5&2i+(-2i)
\end{pmatrix}
\]

\[
=\begin{pmatrix}
4&4-i&3+i\\
4+i&8&6-i\\
3-i&6+i&0
\end{pmatrix}.
\]

Divide every entry by \(2\):

\[
H=\frac12\begin{pmatrix}
4&4-i&3+i\\
4+i&8&6-i\\
3-i&6+i&0
\end{pmatrix}
\]

\[
=\begin{pmatrix}
4/2&(4-i)/2&(3+i)/2\\
(4+i)/2&8/2&(6-i)/2\\
(3-i)/2&(6+i)/2&0/2
\end{pmatrix}
\]

\[
=\boxed{\begin{pmatrix}
2&2-\frac{i}{2}&\frac32+\frac{i}{2}\\
2+\frac{i}{2}&4&3-\frac{i}{2}\\
\frac32-\frac{i}{2}&3+\frac{i}{2}&0
\end{pmatrix}}.
\]

Check: the entry in position \((2,1)\), \(2+\frac{i}{2}\), is the conjugate of the entry in position \((1,2)\), \(2-\frac{i}{2}\). The same happens for the other reflected pairs. The diagonal entries are \(2\), \(4\), and \(0\), all real. Hence \(H^\dagger=H\), so this is indeed the Hermitian part.
