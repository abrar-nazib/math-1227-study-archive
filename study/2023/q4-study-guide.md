# Math 1227 — 2023 Q4 study guide

Read [Matrix adjoint, symmetry, and Hermitian matrices](../concepts/matrix-adjoint-symmetry-and-hermitian.md) for definitions, then [Matrix products, powers, and orthogonality](../concepts/matrix-products-powers-and-orthogonality.md) for the new methods.

## Q4(a) Product of symmetric matrices

> Define matrix and symmetric matrix. If \(A\) and \(B\) are \(n\)-squared symmetric matrices then prove that \(AB\) is symmetric if and only if \(A\) and \(B\) are commutative matrices.

### Underlying-concept map

1. “\(n\)-squared” means an \(n\times n\) square matrix.
2. Symmetry means \(A^T=A\) and \(B^T=B\).
3. Transposing a product reverses order: \((AB)^T=B^TA^T\).
4. “If and only if” requires a proof in both directions.

### Solve it yourself

1. Start by calculating \((AB)^T\), then replace \(A^T,B^T\) using symmetry.
2. In one direction use \((AB)^T=AB\); in the other use \(AB=BA\).

### Detailed answer

Following the class notes, a **matrix of order \(m\times n\)** is an arrangement of \(mn\) numbers in a rectangular array of \(m\) rows and \(n\) columns. A real square matrix \(M=(m_{ij})\) is **symmetric** when the entry at row \(i\), column \(j\) equals the reflected entry at row \(j\), column \(i\):

\[
m_{ij}=m_{ji}\quad\text{for all }i,j.
\]

Equivalently, its transpose is unchanged:

\[
M^T=M.
\]

Since \(A\) and \(B\) are symmetric,

\[
A^T=A,\qquad B^T=B.
\]

Use the transpose-of-product rule:

\[
(AB)^T=B^TA^T=BA.
\]

#### If \(AB\) is symmetric, then \(A\) and \(B\) commute

If \(AB\) is symmetric, then

\[
(AB)^T=AB.
\]

But \((AB)^T=BA\). Hence

\[
BA=AB.
\]

Thus \(A\) and \(B\) commute.

#### If \(A\) and \(B\) commute, then \(AB\) is symmetric

If \(A\) and \(B\) commute, then

\[
AB=BA.
\]

Using \((AB)^T=BA\),

\[
(AB)^T=BA=AB.
\]

This is the definition that \(AB\) is symmetric. Therefore

\[
\boxed{AB\text{ is symmetric if and only if }AB=BA.}
\]

## Q4(b) A power of a special matrix

> Given \(A=\begin{pmatrix}11&-25\\4&-9\end{pmatrix}\), prove that \(A^n=\begin{pmatrix}1+10n&-25n\\4n&1-10n\end{pmatrix}\).

### Underlying-concept map

1. Write \(A=I+N\).
2. Calculate \(N^2\). This question is designed so that it is zero.
3. Prove \(A^n=I+nN\) by induction.
4. Substitute the actual \(N\).

### Solve it yourself

1. Find \(N=A-I\), then multiply \(N\) by itself.
2. Prove the base case \(n=1\).
3. Assuming the result at \(n=k\), multiply by \(A=I+N\).

### Detailed answer

Let

\[
I=\begin{pmatrix}1&0\\0&1\end{pmatrix}.
\]

\[
N=A-I
=\begin{pmatrix}11&-25\\4&-9\end{pmatrix}
-\begin{pmatrix}1&0\\0&1\end{pmatrix}
=\begin{pmatrix}10&-25\\4&-10\end{pmatrix}.
\]

Thus \(A=I+N\). Now

\[
N^2=
\begin{pmatrix}10&-25\\4&-10\end{pmatrix}
\begin{pmatrix}10&-25\\4&-10\end{pmatrix}.
\]

\[
=\begin{pmatrix}
10(10)+(-25)(4)&10(-25)+(-25)(-10)\\
4(10)+(-10)(4)&4(-25)+(-10)(-10)
\end{pmatrix}.
\]

\[
=\begin{pmatrix}100-100&-250+250\\40-40&-100+100\end{pmatrix}
=\begin{pmatrix}0&0\\0&0\end{pmatrix}.
\]

Therefore \(N^2=0\). We prove by induction that

\[
A^n=I+nN
\]

for every positive integer \(n\).

For \(n=1\),

\[
A^1=A=I+N=I+1N.
\]

Assume it is true at \(n=k\):

\[
A^k=I+kN.
\]

Then

\[
A^{k+1}=A^kA=(I+kN)(I+N).
\]

\[
=I\cdot I+I\cdot N+kN\cdot I+kN\cdot N.
\]

\[
=I+N+kN+kN^2.
\]

\[
=I+N+kN+k(0)=I+(k+1)N.
\]

Thus truth at \(k\) implies truth at \(k+1\); with the base case, induction proves \(A^n=I+nN\).

\[
A^n=
\begin{pmatrix}1&0\\0&1\end{pmatrix}
+
n\begin{pmatrix}10&-25\\4&-10\end{pmatrix}.
\]

\[
=\begin{pmatrix}1&0\\0&1\end{pmatrix}
+\begin{pmatrix}10n&-25n\\4n&-10n\end{pmatrix}.
\]

\[
=\boxed{\begin{pmatrix}1+10n&-25n\\4n&1-10n\end{pmatrix}}.
\]

## Q4(c) Orthogonal matrix

> Show that \(A=\begin{pmatrix}\cos\alpha&\sin\alpha\\-\sin\alpha&\cos\alpha\end{pmatrix}\) is orthogonal.

### Underlying-concept map

1. Orthogonal means \(A^TA=I\).
2. Form the transpose, multiply row by column, and use \(\sin^2\alpha+\cos^2\alpha=1\).

### Solve it yourself

1. Write \(A^T\).
2. Calculate all four entries of \(A^TA\).

### Detailed answer

A real square matrix is orthogonal if

\[
A^TA=I.
\]

\[
A=\begin{pmatrix}\cos\alpha&\sin\alpha\\-\sin\alpha&\cos\alpha\end{pmatrix},
\qquad
A^T=\begin{pmatrix}\cos\alpha&-\sin\alpha\\\sin\alpha&\cos\alpha\end{pmatrix}.
\]

\[
A^TA=
\begin{pmatrix}\cos\alpha&-\sin\alpha\\\sin\alpha&\cos\alpha\end{pmatrix}
\begin{pmatrix}\cos\alpha&\sin\alpha\\-\sin\alpha&\cos\alpha\end{pmatrix}.
\]

\[
=\begin{pmatrix}
(\cos\alpha)(\cos\alpha)+(-\sin\alpha)(-\sin\alpha)&
(\cos\alpha)(\sin\alpha)+(-\sin\alpha)(\cos\alpha)\\
(\sin\alpha)(\cos\alpha)+(\cos\alpha)(-\sin\alpha)&
(\sin\alpha)(\sin\alpha)+(\cos\alpha)(\cos\alpha)
\end{pmatrix}.
\]

\[
=\begin{pmatrix}
\cos^2\alpha+\sin^2\alpha&\cos\alpha\sin\alpha-\sin\alpha\cos\alpha\\
\sin\alpha\cos\alpha-\cos\alpha\sin\alpha&\sin^2\alpha+\cos^2\alpha
\end{pmatrix}.
\]

[Trigonometric identity: \(\sin^2\alpha+\cos^2\alpha=1\).]

\[
=\begin{pmatrix}1&0\\0&1\end{pmatrix}=I.
\]

Therefore

\[
\boxed{A^TA=I},
\]

so \(A\) is orthogonal.
