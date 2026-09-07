# Math 1227 — 2024 Q5 study guide

Read [Eigenvalues, eigenvectors, and linear systems](../concepts/eigenvalues-eigenvectors-and-linear-systems.md) first. It explains the two methods used here without duplicating them in this guide.

## Q5(a) Eigenvalues and corresponding eigenvectors

> Find the eigen values and the corresponding eigen vectors of \(A=\begin{pmatrix}1&1&-2\\-1&2&1\\0&1&-1\end{pmatrix}\).

### Underlying-concept map

1. An eigenpair satisfies \(A\vec v=\lambda\vec v\), with \(\vec v\ne\vec0\).
2. Find possible \(\lambda\) values from \(\det(A-\lambda I)=0\).
3. For each value, solve \((A-\lambda I)\vec v=\vec0\).
4. Verify each pair by calculating \(A\vec v\).

### Solve it yourself

1. Subtract \(\lambda\) from the three diagonal entries of \(A\).
2. Expand the determinant along the first row, preserving its \(+,-,+\) cofactor signs.
3. Factor the characteristic polynomial.
4. Substitute each root separately. Let one free component equal \(t\), then choose \(t=1\) for a simple eigenvector.

### Detailed answer

Let

\[
A=\begin{pmatrix}
1&1&-2\\
-1&2&1\\
0&1&-1
\end{pmatrix}.
\]

The characteristic equation is

\[
\det(A-\lambda I)=0.
\]

Subtract \(\lambda\) from the diagonal entries:

\[
A-\lambda I
=\begin{pmatrix}
1-\lambda&1&-2\\
-1&2-\lambda&1\\
0&1&-1-\lambda
\end{pmatrix}.
\]

Expand the determinant along the first row. The cofactor signs are \(+,-,+\):

\[
\det(A-\lambda I)
=(1-\lambda)\begin{vmatrix}2-\lambda&1\\1&-1-\lambda\end{vmatrix}
-1\begin{vmatrix}-1&1\\0&-1-\lambda\end{vmatrix}
+(-2)\begin{vmatrix}-1&2-\lambda\\0&1\end{vmatrix}.
\]

Evaluate the three \(2\times2\) determinants:

\[
\det(A-\lambda I)
=(1-\lambda)\bigl((2-\lambda)(-1-\lambda)-1\cdot1\bigr)
-\bigl((-1)(-1-\lambda)-1\cdot0\bigr)
+(-2)\bigl((-1)\cdot1-(2-\lambda)\cdot0\bigr).
\]

\[
(2-\lambda)(-1-\lambda)
=-2-2\lambda+\lambda+\lambda^2
=\lambda^2-\lambda-2.
\]

Therefore

\[
\det(A-\lambda I)
=(1-\lambda)\bigl((\lambda^2-\lambda-2)-1\bigr)
-\bigl(1+\lambda\bigr)
+(-2)(-1).
\]

\[
= (1-\lambda)(\lambda^2-\lambda-3)-1-\lambda+2.
\]

Expand the first product:

\[
(1-\lambda)(\lambda^2-\lambda-3)
=\lambda^2-\lambda-3-\lambda^3+\lambda^2+3\lambda
=-\lambda^3+2\lambda^2+2\lambda-3.
\]

Hence

\[
\det(A-\lambda I)
=-\lambda^3+2\lambda^2+2\lambda-3-1-\lambda+2
\]

\[
=-\lambda^3+2\lambda^2+\lambda-2.
\]

Set this equal to zero:

\[
-\lambda^3+2\lambda^2+\lambda-2=0.
\]

Multiply both sides by \(-1\):

\[
\lambda^3-2\lambda^2-\lambda+2=0.
\]

Factor by grouping:

\[
\lambda^2(\lambda-2)-1(\lambda-2)=0,
\]

\[
(\lambda^2-1)(\lambda-2)=0,
\]

\[
(\lambda-1)(\lambda+1)(\lambda-2)=0.
\]

Thus the eigenvalues are

\[
\lambda=-1,\qquad\lambda=1,\qquad\lambda=2.
\]

#### Eigenvector for \(\lambda=-1\)

Substitute \(\lambda=-1\):

\[
A-(-1)I=A+I
=\begin{pmatrix}
2&1&-2\\
-1&3&1\\
0&1&0
\end{pmatrix}.
\]

Let \(\vec v=(x,y,z)^T\). From \((A+I)\vec v=\vec0\),

\[
2x+y-2z=0,
\]

\[
-x+3y+z=0,
\]

\[
y=0.
\]

Put \(y=0\) in the first equation:

\[
2x+0-2z=0,
\]

\[
2x=2z,
\]

\[
x=z.
\]

Choose \(z=1\). Then \(x=1\) and \(y=0\), so one eigenvector is

\[
\vec v_{-1}=\begin{pmatrix}1\\0\\1\end{pmatrix}.
\]

Check:

\[
A\vec v_{-1}
=\begin{pmatrix}1&1&-2\\-1&2&1\\0&1&-1\end{pmatrix}
\begin{pmatrix}1\\0\\1\end{pmatrix}
=\begin{pmatrix}1\cdot1+1\cdot0-2\cdot1\\-1\cdot1+2\cdot0+1\cdot1\\0\cdot1+1\cdot0-1\cdot1\end{pmatrix}
=\begin{pmatrix}-1\\0\\-1\end{pmatrix}
=(-1)\begin{pmatrix}1\\0\\1\end{pmatrix}.
\]

#### Eigenvector for \(\lambda=1\)

Substitute \(\lambda=1\):

\[
A-I
=\begin{pmatrix}
0&1&-2\\
-1&1&1\\
0&1&-2
\end{pmatrix}.
\]

From \((A-I)\vec v=\vec0\),

\[
y-2z=0,
\]

\[
-x+y+z=0.
\]

The first equation gives

\[
y=2z.
\]

Substitute \(y=2z\) into the second equation:

\[
-x+2z+z=0,
\]

\[
-x+3z=0,
\]

\[
x=3z.
\]

Choose \(z=1\). Then \(x=3\) and \(y=2\), so one eigenvector is

\[
\vec v_1=\begin{pmatrix}3\\2\\1\end{pmatrix}.
\]

Check:

\[
A\vec v_1
=\begin{pmatrix}1&1&-2\\-1&2&1\\0&1&-1\end{pmatrix}
\begin{pmatrix}3\\2\\1\end{pmatrix}
=\begin{pmatrix}1\cdot3+1\cdot2-2\cdot1\\-1\cdot3+2\cdot2+1\cdot1\\0\cdot3+1\cdot2-1\cdot1\end{pmatrix}
=\begin{pmatrix}3\\2\\1\end{pmatrix}
=1\begin{pmatrix}3\\2\\1\end{pmatrix}.
\]

#### Eigenvector for \(\lambda=2\)

Substitute \(\lambda=2\):

\[
A-2I
=\begin{pmatrix}
-1&1&-2\\
-1&0&1\\
0&1&-3
\end{pmatrix}.
\]

From \((A-2I)\vec v=\vec0\),

\[
-x+y-2z=0,
\]

\[
-x+z=0,
\]

\[
y-3z=0.
\]

The second equation gives

\[
x=z.
\]

The third equation gives

\[
y=3z.
\]

Choose \(z=1\). Then \(x=1\) and \(y=3\). Check the first equation before choosing the vector:

\[
-x+y-2z=-z+3z-2z=0.
\]

Thus one eigenvector is

\[
\vec v_2=\begin{pmatrix}1\\3\\1\end{pmatrix}.
\]

Check:

\[
A\vec v_2
=\begin{pmatrix}1&1&-2\\-1&2&1\\0&1&-1\end{pmatrix}
\begin{pmatrix}1\\3\\1\end{pmatrix}
=\begin{pmatrix}1\cdot1+1\cdot3-2\cdot1\\-1\cdot1+2\cdot3+1\cdot1\\0\cdot1+1\cdot3-1\cdot1\end{pmatrix}
=\begin{pmatrix}2\\6\\2\end{pmatrix}
=2\begin{pmatrix}1\\3\\1\end{pmatrix}.
\]

Every nonzero scalar multiple of each displayed vector is also a corresponding eigenvector.

## Q5(b) Solve by matrix method

> Solve by matrix method: \(x-y+2z=3\), \(x+2y+3z=5\), \(3x-4y-5z=-13\).

### Underlying-concept map

1. Put the coefficients and right-hand sides into one augmented matrix.
2. Use valid row operations to remove \(x\), then remove \(y\).
3. Read the final row to get \(z\), then substitute upward to get \(y\) and \(x\).
4. Substitute the answer into all three original equations.

### Solve it yourself

1. Use the first row as the first pivot. Replace \(R_2\) by \(R_2-R_1\), and \(R_3\) by \(R_3-3R_1\).
2. Combine the new second and third rows to eliminate the \(-1\) in the second column without fractions.
3. Solve the triangular equations from bottom to top.

### Detailed answer

Write the system as the augmented matrix

\[
\left[\begin{array}{ccc|c}
1&-1&2&3\\
1&2&3&5\\
3&-4&-5&-13
\end{array}\right].
\]

First eliminate \(x\) from row 2:

\[
R_2\to R_2-R_1.
\]

The new second row is

\[
(1,2,3\mid5)-(1,-1,2\mid3)
=(1-1,\ 2-(-1),\ 3-2\mid5-3)
=(0,3,1\mid2).
\]

Next eliminate \(x\) from row 3:

\[
R_3\to R_3-3R_1.
\]

The new third row is

\[
(3,-4,-5\mid-13)-3(1,-1,2\mid3)
\]

\[
=(3,-4,-5\mid-13)-(3,-3,6\mid9)
\]

\[
=(3-3,\ -4-(-3),\ -5-6\mid-13-9)
=(0,-1,-11\mid-22).
\]

The augmented matrix is now

\[
\left[\begin{array}{ccc|c}
1&-1&2&3\\
0&3&1&2\\
0&-1&-11&-22
\end{array}\right].
\]

Eliminate \(y\) in row 3 without introducing fractions. Three copies of row 3 have second entry \(-3\), which cancels the \(+3\) in row 2:

\[
R_3\to 3R_3+R_2.
\]

\[
3(0,-1,-11\mid-22)+(0,3,1\mid2)
\]

\[
=(0,-3,-33\mid-66)+(0,3,1\mid2)
\]

\[
=(0,-3+3,-33+1\mid-66+2)
=(0,0,-32\mid-64).
\]

Thus

\[
\left[\begin{array}{ccc|c}
1&-1&2&3\\
0&3&1&2\\
0&0&-32&-64
\end{array}\right].
\]

The last row represents

\[
-32z=-64.
\]

Divide both sides by \(-32\):

\[
z=\frac{-64}{-32}=2.
\]

The second row represents

\[
3y+z=2.
\]

Substitute \(z=2\):

\[
3y+2=2,
\]

\[
3y=0,
\]

\[
y=0.
\]

The first row represents

\[
x-y+2z=3.
\]

Substitute \(y=0\) and \(z=2\):

\[
x-0+2(2)=3,
\]

\[
x+4=3,
\]

\[
x=-1.
\]

Therefore

\[
\boxed{x=-1,\qquad y=0,\qquad z=2.}
\]

Check in the original equations:

\[
x-y+2z=-1-0+2(2)=-1+4=3,
\]

\[
x+2y+3z=-1+2(0)+3(2)=-1+6=5,
\]

\[
3x-4y-5z=3(-1)-4(0)-5(2)=-3-10=-13.
\]

All three equations are satisfied.
