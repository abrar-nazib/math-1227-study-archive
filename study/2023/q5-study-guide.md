# Math 1227 — 2023 Q5 study guide

Read [Eigenvalues, eigenvectors, and solving linear systems](../concepts/eigenvalues-eigenvectors-and-linear-systems.md) first. It explains the reusable methods used in both parts.

## Q5(a) When does a system have a solution?

> For what values of \(\lambda\), the system \(x+y+z=1\), \(x+2y+4z=\lambda\), \(x+4y+10z=\lambda^2\) has a solution. Solve them completely in each case.

### Underlying-concept map

1. A solution must satisfy all three equations at once.
2. Subtracting equations eliminates \(x\).
3. The second difference must be twice the first difference on the left, so its right-hand side must obey the same relationship.
4. Once \(\lambda\) is known, one variable remains free; that gives all solutions.

### Solve it yourself

1. Calculate equation 2 minus equation 1.
2. Calculate equation 3 minus equation 2.
3. Compare the left sides, then impose the same relation on the right sides.
4. Solve the resulting quadratic for \(\lambda\).
5. Substitute each value separately, let \(z=t\), and solve for \(x,y\).

### Detailed answer

Name the three equations:

\[
E_1:\quad x+y+z=1,
\]

\[
E_2:\quad x+2y+4z=\lambda,
\]

\[
E_3:\quad x+4y+10z=\lambda^2.
\]

Subtract \(E_1\) from \(E_2\):

\[
(x+2y+4z)-(x+y+z)=\lambda-1.
\]

\[
x+2y+4z-x-y-z=\lambda-1.
\]

\[
y+3z=\lambda-1.
\]

Subtract \(E_2\) from \(E_3\):

\[
(x+4y+10z)-(x+2y+4z)=\lambda^2-\lambda.
\]

\[
x+4y+10z-x-2y-4z=\lambda^2-\lambda.
\]

\[
2y+6z=\lambda^2-\lambda.
\]

But the left side here is twice the first difference:

\[
2y+6z=2(y+3z).
\]

Since \(y+3z=\lambda-1\), a solution can exist only if

\[
\lambda^2-\lambda=2(\lambda-1).
\]

\[
\lambda^2-\lambda=2\lambda-2.
\]

\[
\lambda^2-3\lambda+2=0.
\]

\[
(\lambda-1)(\lambda-2)=0.
\]

Thus

\[
\lambda=1
\qquad\text{or}\qquad
\lambda=2.
\]

### Case 1: \(\lambda=1\)

The difference equation becomes

\[
y+3z=1-1=0.
\]

Let

\[
z=t.
\]

\[
y+3t=0.
\]

\[
y=-3t.
\]

Use \(E_1\):

\[
x+y+z=1.
\]

\[
x+(-3t)+t=1.
\]

\[
x-2t=1.
\]

\[
x=1+2t.
\]

Therefore all solutions when \(\lambda=1\) are

\[
\boxed{(x,y,z)=(1+2t,-3t,t),\qquad t\in\mathbb R.}
\]

Check in \(E_3\):

\[
x+4y+10z=(1+2t)+4(-3t)+10t.
\]

\[
=1+2t-12t+10t=1=1^2.
\]

### Case 2: \(\lambda=2\)

The first difference becomes

\[
y+3z=2-1=1.
\]

Let

\[
z=t.
\]

\[
y+3t=1.
\]

\[
y=1-3t.
\]

Use \(E_1\):

\[
x+(1-3t)+t=1.
\]

\[
x+1-2t=1.
\]

\[
x=2t.
\]

Therefore all solutions when \(\lambda=2\) are

\[
\boxed{(x,y,z)=(2t,1-3t,t),\qquad t\in\mathbb R.}
\]

Check in \(E_3\):

\[
x+4y+10z=2t+4(1-3t)+10t.
\]

\[
=2t+4-12t+10t=4=2^2.
\]

## Q5(b) Eigenvalues and eigenvectors

> Define eigen value and eigen vector. Find the eigen value and corresponding eigen vectors of \(A=\begin{pmatrix}1&-3&3\\3&-5&3\\6&-6&4\end{pmatrix}\).

### Underlying-concept map

1. Following the class notes, the roots of the characteristic equation are eigenvalues.
2. For each root, a corresponding nonzero vector solves \((A-\lambda I)\vec v=\vec0\).
3. Find the characteristic equation by calculating \(\det(A-\lambda I)=0\).
4. Solve the zero-right-hand-side system separately for each eigenvalue.

### Solve it yourself

1. State the class-note definition in the answer.
2. Form \(A-\lambda I\) by subtracting \(\lambda\) only from diagonal entries.
3. Expand its determinant and factor it.
4. Substitute each eigenvalue into \(A-\lambda I\), row-reduce, and keep the free variables.

### Detailed answer

Following the class notes: for a square matrix \(A\), the roots of the characteristic equation

\[
\det(A-\lambda I)=0
\]

are called the **eigenvalues** (or characteristic roots). For each eigenvalue \(\lambda\), every corresponding nonzero vector \(\vec v\) satisfying

\[
(A-\lambda I)\vec v=\vec0
\]

is an **eigenvector** (or characteristic vector).

Let

\[
A=\begin{pmatrix}1&-3&3\\3&-5&3\\6&-6&4\end{pmatrix}.
\]

\[
A-\lambda I=
\begin{pmatrix}
1-\lambda&-3&3\\
3&-5-\lambda&3\\
6&-6&4-\lambda
\end{pmatrix}.
\]

Expand along the first row:

\[
\det(A-\lambda I)
=(1-\lambda)\begin{vmatrix}-5-\lambda&3\\-6&4-\lambda\end{vmatrix}
-(-3)\begin{vmatrix}3&3\\6&4-\lambda\end{vmatrix}
+3\begin{vmatrix}3&-5-\lambda\\6&-6\end{vmatrix}.
\]

\[
=(1-\lambda)\left[(-5-\lambda)(4-\lambda)-3(-6)\right]
+3\left[3(4-\lambda)-3(6)\right]
+3\left[3(-6)-(-5-\lambda)(6)\right].
\]

\[
(-5-\lambda)(4-\lambda)=-20+5\lambda-4\lambda+\lambda^2
=\lambda^2+\lambda-20.
\]

\[
\det(A-\lambda I)
=(1-\lambda)(\lambda^2+\lambda-20+18)
+3(12-3\lambda-18)
+3(-18+30+6\lambda).
\]

\[
=(1-\lambda)(\lambda^2+\lambda-2)
+3(-6-3\lambda)
+3(12+6\lambda).
\]

\[
\lambda^2+\lambda-2=(\lambda+2)(\lambda-1).
\]

\[
(1-\lambda)(\lambda^2+\lambda-2)
=-(\lambda-1)(\lambda+2)(\lambda-1)
=-(\lambda-1)^2(\lambda+2).
\]

\[
3(-6-3\lambda)=-18-9\lambda.
\]

\[
3(12+6\lambda)=36+18\lambda.
\]

\[
\det(A-\lambda I)
=-(\lambda-1)^2(\lambda+2)-18-9\lambda+36+18\lambda.
\]

\[
=-(\lambda-1)^2(\lambda+2)+18+9\lambda.
\]

\[
=-\left(\lambda^3-3\lambda+2\right)+18+9\lambda.
\]

\[
=-\lambda^3+3\lambda-2+18+9\lambda.
\]

\[
=-\lambda^3+12\lambda+16.
\]

\[
=-\left(\lambda^3-12\lambda-16\right).
\]

\[
=-(\lambda-4)(\lambda+2)^2.
\]

The characteristic equation is

\[
-(\lambda-4)(\lambda+2)^2=0.
\]

Thus the eigenvalues are

\[
\lambda=4
\qquad\text{and}\qquad
\lambda=-2.
\]

### Eigenvectors for \(\lambda=4\)

\[
A-4I=
\begin{pmatrix}-3&-3&3\\3&-9&3\\6&-6&0\end{pmatrix}.
\]

Let \(\vec v=\begin{pmatrix}x\\y\\z\end{pmatrix}\). Then

\[
-3x-3y+3z=0,\qquad
3x-9y+3z=0,\qquad
6x-6y=0.
\]

\[
6x=6y.
\]

\[
x=y.
\]

Substitute \(y=x\) into the first equation:

\[
-3x-3x+3z=0.
\]

\[
-6x+3z=0.
\]

\[
z=2x.
\]

Let \(x=t\):

\[
\vec v=\begin{pmatrix}t\\t\\2t\end{pmatrix}
=t\begin{pmatrix}1\\1\\2\end{pmatrix}.
\]

Thus every nonzero multiple of

\[
\boxed{\begin{pmatrix}1\\1\\2\end{pmatrix}}
\]

is an eigenvector for \(\lambda=4\). Check:

\[
A\begin{pmatrix}1\\1\\2\end{pmatrix}
=\begin{pmatrix}1-3+6\\3-5+6\\6-6+8\end{pmatrix}
=\begin{pmatrix}4\\4\\8\end{pmatrix}
=4\begin{pmatrix}1\\1\\2\end{pmatrix}.
\]

### Eigenvectors for \(\lambda=-2\)

\[
A-(-2)I=A+2I
=\begin{pmatrix}3&-3&3\\3&-3&3\\6&-6&6\end{pmatrix}.
\]

All rows give the same equation:

\[
3x-3y+3z=0.
\]

\[
x-y+z=0.
\]

Let

\[
y=s,\qquad z=t.
\]

\[
x-s+t=0.
\]

\[
x=s-t.
\]

\[
\vec v=
\begin{pmatrix}s-t\\s\\t\end{pmatrix}
=s\begin{pmatrix}1\\1\\0\end{pmatrix}
+t\begin{pmatrix}-1\\0\\1\end{pmatrix}.
\]

Thus the eigenvectors for \(\lambda=-2\) are all nonzero vectors

\[
\boxed{
s\begin{pmatrix}1\\1\\0\end{pmatrix}
+t\begin{pmatrix}-1\\0\\1\end{pmatrix},
\qquad(s,t)\ne(0,0).}
\]

Check both basis vectors:

\[
A\begin{pmatrix}1\\1\\0\end{pmatrix}
=\begin{pmatrix}1-3+0\\3-5+0\\6-6+0\end{pmatrix}
=\begin{pmatrix}-2\\-2\\0\end{pmatrix}
=-2\begin{pmatrix}1\\1\\0\end{pmatrix}.
\]

\[
A\begin{pmatrix}-1\\0\\1\end{pmatrix}
=\begin{pmatrix}-1+0+3\\-3+0+3\\-6+0+4\end{pmatrix}
=\begin{pmatrix}2\\0\\-2\end{pmatrix}
=-2\begin{pmatrix}-1\\0\\1\end{pmatrix}.
\]
