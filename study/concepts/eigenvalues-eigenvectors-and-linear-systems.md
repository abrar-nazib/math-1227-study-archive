# Eigenvalues, eigenvectors, and solving linear systems

This note contains the two new matrix ideas needed for 2024 Q5: a direction that a matrix transformation does not turn, and a systematic way to solve several linear equations together.

## Before starting: the objects in this note

A **matrix** is a rectangular array of numbers. You can treat it as a rule or machine: it receives a column of numbers and produces another column of numbers. A **vector** is such a column; geometrically, it can be pictured as an arrow from the origin. Its components tell how far the arrow moves in each coordinate direction.

For example,

\[
A=\begin{pmatrix}2&1\\0&3\end{pmatrix},
\qquad
\vec v=\begin{pmatrix}x\\y\end{pmatrix}.
\]

Matrix multiplication applies one row at a time:

\[
A\vec v
=\begin{pmatrix}2&1\\0&3\end{pmatrix}
\begin{pmatrix}x\\y\end{pmatrix}
=\begin{pmatrix}2x+1y\\0x+3y\end{pmatrix}
=\begin{pmatrix}2x+y\\3y\end{pmatrix}.
\]

The vector is the **input**, and \(A\vec v\) is the **output**. A **scalar** is just one ordinary number, such as \(2\), \(-1\), or \(\tfrac12\). Multiplying a vector by a scalar stretches, shrinks, or reverses its arrow without changing its line of direction.

## 1. Eigenvalues and eigenvectors

Think of a matrix as a machine that takes an arrow (a vector) and produces a new arrow. Most input arrows are both stretched and turned. An **eigenvector** is a special nonzero arrow that is not turned: the machine only stretches it, shrinks it, or reverses it. The stretch factor is its **eigenvalue**.

The word **nonzero** matters. The zero vector has no direction, and every matrix sends it to the zero vector. It would satisfy the equation for every value of \(\lambda\), so it tells us nothing useful about the transformation.

### A small pictureable example

Consider

\[
D=\begin{pmatrix}2&0\\0&1\end{pmatrix}.
\]

This machine doubles the horizontal component of every arrow and leaves the vertical component unchanged. Apply it to the horizontal arrow:

\[
D\begin{pmatrix}1\\0\end{pmatrix}
=\begin{pmatrix}2\cdot1+0\cdot0\\0\cdot1+1\cdot0\end{pmatrix}
=\begin{pmatrix}2\\0\end{pmatrix}
=2\begin{pmatrix}1\\0\end{pmatrix}.
\]

The output stays horizontal, so \(\begin{pmatrix}1\\0\end{pmatrix}\) is an eigenvector and its eigenvalue is \(2\). Now apply it to the vertical arrow:

\[
D\begin{pmatrix}0\\1\end{pmatrix}
=\begin{pmatrix}2\cdot0+0\cdot1\\0\cdot0+1\cdot1\end{pmatrix}
=\begin{pmatrix}0\\1\end{pmatrix}
=1\begin{pmatrix}0\\1\end{pmatrix}.
\]

That arrow also keeps its direction, and its eigenvalue is \(1\). An eigenvalue of \(-1\) would reverse an eigenvector; an eigenvalue between \(-1\) and \(1\) would shrink it.

> [!IMPORTANT]
> **Exam formula — eigenvalue and eigenvector relation**
>
> \[
> A\vec v=\lambda\vec v,\qquad \vec v\ne\vec0.
> \]
>
> \(\lambda\) is an eigenvalue and \(\vec v\) is a corresponding eigenvector.

Move the right side to the left. This makes a **homogeneous system**, meaning a system whose right-hand side is the zero vector. Its nonzero solutions are the desired eigenvectors:

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

The **identity matrix** is the matrix version of multiplying by \(1\): it leaves a vector unchanged. For a \(3\times3\) problem,

\[
I=\begin{pmatrix}1&0&0\\0&1&0\\0&0&1\end{pmatrix},
\qquad
I\begin{pmatrix}x\\y\\z\end{pmatrix}
=\begin{pmatrix}x\\y\\z\end{pmatrix}.
\]

Thus \(\lambda I\vec v=\lambda\vec v\). This explains the move from \(A\vec v=\lambda\vec v\) to \((A-\lambda I)\vec v=\vec0\): both terms now involve the same vector \(\vec v\).

### Why the determinant is set to zero

The **determinant** of a square matrix is one number that detects whether the matrix flattens space in some direction. For a \(2\times2\) matrix it is calculated as follows:

> [!IMPORTANT]
> **Exam formula — determinant of a \(2\times2\) matrix**
>
> \[
> \begin{vmatrix}a&b\\c&d\end{vmatrix}=ad-bc.
> \]

### Expanding a \(3\times3\) determinant along the first row

For a \(3\times3\) determinant, **cofactor expansion** means breaking it into three \(2\times2\) determinants. Choose one row or column. In Q5 we choose the first row because its signs follow the easy pattern \(+,-,+\):

> [!IMPORTANT]
> **Exam formula — first-row cofactor expansion**
>
> \[
> \begin{vmatrix}a&b&c\\d&e&f\\g&h&i\end{vmatrix}
> =a\begin{vmatrix}e&f\\h&i\end{vmatrix}
> -b\begin{vmatrix}d&f\\g&i\end{vmatrix}
> +c\begin{vmatrix}d&e\\g&h\end{vmatrix}.
> \]

To make the first small determinant, cover the first entry \(a\), then delete its entire row and column; the four uncovered entries are \(e,f,h,i\). Do the same for \(b\) and \(c\). The original entries \(a,b,c\) stay in front as multipliers. The middle term is subtracted because its cofactor sign is negative.

The safe order is always:

1. write the three terms with their \(+,-,+\) signs;
2. calculate each small determinant using \(ad-bc\);
3. multiply by the original first-row entry in front of it;
4. add the three resulting contributions.

Do not combine terms before every small determinant has been evaluated. The detailed Q5 calculation applies this exact routine.

If a matrix has determinant \(0\), it is called **singular**. It squashes at least one nonzero input vector down to the zero vector. If its determinant is not zero, it is **non-singular** and no nonzero vector can be sent to zero.

We need \((A-\lambda I)\vec v=\vec0\) to have a nonzero vector \(\vec v\). Therefore \(A-\lambda I\) must be singular:

\[
\det(A-\lambda I)=0.
\]

This equation is called the **characteristic equation**. Its roots, meaning the values of \(\lambda\) that make it true, are the eigenvalues. The expression before setting it equal to zero is the **characteristic polynomial**.

### A reliable exam routine

1. Form \(A-\lambda I\): subtract \(\lambda\) from diagonal entries only.
2. Expand \(\det(A-\lambda I)\), set it to zero, and factor to find \(\lambda\).
3. For one eigenvalue at a time, substitute it into \((A-\lambda I)\vec v=\vec0\).
4. Solve for \(x,y,z\), leaving one **free variable** such as \(z=t\). A free variable is a component not fixed by the equations; choosing a nonzero value for it produces one eigenvector. Any nonzero multiple of that vector is also an eigenvector.
5. Check by multiplying \(A\vec v\), and compare with \(\lambda\vec v\).

## 2. Linear systems as one matrix

A **linear equation** has unknowns only to the first power and no products such as \(xy\). For example, \(2x-y+3z=5\) is linear. A **system of linear equations** is several such equations that must be true at the same time. A **solution** is one set of values, such as \((x,y,z)\), that makes every equation true simultaneously.

Each equation contributes three types of information:

- a **coefficient** is the number multiplying an unknown, such as \(2\) in \(2x-y+3z=5\);
- a **constant term** is a number with no unknown, such as the \(5\) on the right;
- the order of the unknowns must stay fixed. If columns mean \(x,y,z\), every row must use exactly that order.

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

Here \(A\) is the **coefficient matrix**, \(\vec x=(x,y,z)^T\) is the **unknown vector**, and \(\vec b\) is the **constant vector** of right-hand sides. The superscript \(T\) means “write the listed components as a column”; see [the transpose section](matrix-adjoint-symmetry-and-hermitian.md#1-transpose-reflecting-entries-across-the-main-diagonal) if that notation needs a refresh. The **augmented matrix** keeps the equations in rows while placing a divider before the right-hand side:

\[
\left[\begin{array}{ccc|c}
a_{11}&a_{12}&a_{13}&b_1\\
a_{21}&a_{22}&a_{23}&b_2\\
a_{31}&a_{32}&a_{33}&b_3
\end{array}\right].
\]

Each row is one equation. **Row operations** simply replace an equation by an equivalent equation, so they do not change the solution set:

- swapping two rows only changes the order in which the equations are written;
- multiplying a row by a nonzero number multiplies both sides of one equation by that same nonzero number;
- adding a multiple of one row to another adds a multiple of one equation to another, which makes an equivalent equation.

> [!IMPORTANT]
> **Exam rule — valid row operations**
>
> \[
> R_i\leftrightarrow R_j,\qquad
> R_i\to cR_i\ (c\ne0),\qquad
> R_i\to R_i+cR_j.
> \]

The first nonzero number in a row is called its **pivot** (or leading entry). **Gaussian elimination** uses row operations to make zeros below each pivot. It turns a tangled system into a staircase-shaped, or **triangular**, system. The last row then gives one variable directly; use **back-substitution**, meaning substitute that value into the row above, and continue upward.

### A two-equation elimination example

Start with

\[
x+y=5,
\]

\[
x-y=1.
\]

Its augmented matrix is

\[
\left[\begin{array}{cc|c}1&1&5\\1&-1&1\end{array}\right].
\]

Perform \(R_2\to R_2-R_1\). This means “second equation minus first equation”:

\[
(x-y)-(x+y)=1-5,
\]

\[
x-y-x-y=-4,
\]

\[
-2y=-4,
\]

\[
y=2.
\]

In matrix form, the same operation is

\[
\left[\begin{array}{cc|c}1&1&5\\1&-1&1\end{array}\right]
\longrightarrow
\left[\begin{array}{cc|c}1&1&5\\0&-2&-4\end{array}\right].
\]

Now substitute \(y=2\) into the first equation:

\[
x+2=5,
\]

\[
x=3.
\]

The matrix has not performed a mysterious new kind of arithmetic. It recorded the familiar elimination of variables in a compact, organised form.

### Final check

Always substitute the found \(x,y,z\) into all original equations. This catches a copied sign or row-operation error before it reaches the final answer.
