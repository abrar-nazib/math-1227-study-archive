# Eigenvalues, eigenvectors, and solving linear systems

This note contains the two new matrix ideas needed for 2024 Q5: a direction that a matrix transformation does not turn, and a systematic way to solve several linear equations together.

## 1. Eigenvalues and eigenvectors

Think of a matrix as a machine that takes an arrow (a vector) and produces a new arrow. Most input arrows are both stretched and turned. An **eigenvector** is a special nonzero arrow that is not turned: the machine only stretches it, shrinks it, or reverses it. The stretch factor is its **eigenvalue**.

> [!IMPORTANT]
> **Exam formula — eigenvalue and eigenvector relation**
>
> \[
> A\vec v=\lambda\vec v,\qquad \vec v\ne\vec0.
> \]
>
> \(\lambda\) is an eigenvalue and \(\vec v\) is a corresponding eigenvector.

Move the right side to the left. This makes a homogeneous system whose nonzero solutions are the desired eigenvectors:

> [!IMPORTANT]
> **Exam formulas — characteristic equation and eigenvector equation**
>
> \[
> \det(A-\lambda I)=0,
> \qquad
> (A-\lambda I)\vec v=\vec0.
> \]
>
> \(I\) is the identity matrix, with \(1\) on the main diagonal and \(0\) elsewhere.

Why is the determinant set to zero? A nonzero solution of \((A-\lambda I)\vec v=\vec0\) can exist only when the matrix \(A-\lambda I\) is singular, and a square matrix is singular exactly when its determinant is zero.

### A reliable exam routine

1. Form \(A-\lambda I\): subtract \(\lambda\) from diagonal entries only.
2. Expand \(\det(A-\lambda I)\), set it to zero, and factor to find \(\lambda\).
3. For one eigenvalue at a time, substitute it into \((A-\lambda I)\vec v=\vec0\).
4. Solve for \(x,y,z\), leaving one free variable such as \(z=t\). Any nonzero multiple of the resulting vector is also an eigenvector.
5. Check by multiplying \(A\vec v\), and compare with \(\lambda\vec v\).

## 2. Linear systems as one matrix

The equations

\[
a_{11}x+a_{12}y+a_{13}z=b_1,
\]

\[
a_{21}x+a_{22}y+a_{23}z=b_2,
\]

\[
a_{31}x+a_{32}y+a_{33}z=b_3
\]

can be compressed into

\[
A\vec x=\vec b.
\]

Here \(A\) holds the coefficients, \(\vec x=(x,y,z)^T\) holds the unknowns, and \(\vec b\) holds the right-hand sides. The **augmented matrix** keeps the equations in columns while placing a divider before the right-hand side:

\[
\left[\begin{array}{ccc|c}
a_{11}&a_{12}&a_{13}&b_1\\
a_{21}&a_{22}&a_{23}&b_2\\
a_{31}&a_{32}&a_{33}&b_3
\end{array}\right].
\]

Each row is one equation. Row operations simply replace one equation by an equivalent equation, so they do not change the solution set.

> [!IMPORTANT]
> **Exam rule — valid row operations**
>
> \[
> R_i\leftrightarrow R_j,\qquad
> R_i\to cR_i\ (c\ne0),\qquad
> R_i\to R_i+cR_j.
> \]

**Gaussian elimination** uses these operations to make zeros below the leading entries. Once the final row gives one variable, work upward by substitution. This is often quicker and less error-prone than calculating an inverse by hand.

### Final check

Always substitute the found \(x,y,z\) into all original equations. This catches a copied sign or row-operation error before it reaches the final answer.
