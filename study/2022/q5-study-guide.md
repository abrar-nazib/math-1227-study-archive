# Math 1227 — 2022 Q5 Study Guide

This question has two independent jobs. Part (a) asks when three linear equations agree with each other; part (b) asks for the special directions that a matrix does not turn.

## Concept links

- For the eigenvalue method, including why \(\det(A-\lambda I)=0\), read [Eigenvalues, eigenvectors, and solving linear systems](../concepts/eigenvalues-eigenvectors-and-linear-systems.md#1-eigenvalues-and-eigenvectors).
- For the meaning of matrix rank and row reduction, read [Matrix rank, echelon form, and normal form](../concepts/matrix-rank-echelon-form-and-normal-form.md).

## Q5(a) When does the system have no, one, or infinitely many solutions?

> Determine for what values of \(\lambda\) and \(\mu\) the system
>
> \[
> x+y+z=6,\qquad x+2y+3z=10,\qquad x+2y+\lambda z=\mu
> \]
>
> has: (i) no solution, (ii) a unique solution, (iii) infinitely many solutions.

### Underlying-concept map

The first two equations already place restrictions on \(x,y,z\). The third equation is almost the same as the second: only the coefficient of \(z\), and the right-hand-side number, may differ. That similarity is the clue. Subtracting the second equation from the third removes \(x\) and \(y\), leaving the exact condition that decides the answer.

You need these ideas, in this order:

1. A system has a **unique solution** when it determines every unknown to one value.
2. It has **no solution** when two equations demand an impossible thing, such as \(0=5\).
3. It has **infinitely many solutions** when one equation gives no new restriction because it repeats another equation.
4. Subtracting one whole equation from another is valid because it removes the same quantity from both sides.

### See the three possibilities first

Imagine that the second and third equations are two instructions about the same three unknowns.

- If their left sides are exactly identical but their right sides differ, they are contradictory instructions: no triple \((x,y,z)\) can obey both.
- If both sides are identical, the third instruction is only a duplicate. There are then only two independent equations for three unknowns, leaving one adjustable parameter and infinitely many answers.
- If the third equation has a genuinely different \(z\)-coefficient, it determines \(z\); the first two equations then determine \(y\) and \(x\). That gives one answer.

### Solve it yourself

1. Label the equations \(E_1,E_2,E_3\).
2. Compute \(E_3-E_2\) term by term.
3. Separate the cases \(\lambda\ne3\) and \(\lambda=3\).
4. When \(\lambda=3\), compare \(\mu\) with \(10\).

### Detailed solution

Write the equations as

\[
\begin{aligned}
E_1&:x+y+z=6,\\
E_2&:x+2y+3z=10,\\
E_3&:x+2y+\lambda z=\mu.
\end{aligned}
\]

Subtract \(E_2\) from \(E_3\). On the left, subtract matching terms; on the right, subtract the constants:

\[
\begin{aligned}
&(x+2y+\lambda z)-(x+2y+3z)=\mu-10,\\
&x-x+2y-2y+\lambda z-3z=\mu-10,\\
&(\lambda-3)z=\mu-10.
\end{aligned}
\]

#### Case 1: \(\lambda\ne3\)

Then \(\lambda-3\ne0\), so divide by \(\lambda-3\):

\[
z=\frac{\mu-10}{\lambda-3}.
\]

Now subtract \(E_1\) from \(E_2\):

\[
\begin{aligned}
&(x+2y+3z)-(x+y+z)=10-6,\\
&x-x+2y-y+3z-z=4,\\
&y+2z=4,\\
&y=4-2z.
\end{aligned}
\]

Substitute the already determined value of \(z\):

\[
y=4-2\left(\frac{\mu-10}{\lambda-3}\right).
\]

Use \(E_1\) to find \(x\):

\[
\begin{aligned}
x+y+z&=6,\\
x&=6-y-z,\\
x&=6-(4-2z)-z,\\
x&=6-4+2z-z,\\
x&=2+z,\\
x&=2+\frac{\mu-10}{\lambda-3}.
\end{aligned}
\]

Every variable now has exactly one value. Therefore:

\[
\boxed{\lambda\ne3\quad\Longrightarrow\quad\text{a unique solution for every }\mu.}
\]

#### Case 2: \(\lambda=3\)

The third equation becomes

\[
x+2y+3z=\mu.
\]

But \(E_2\) is

\[
x+2y+3z=10.
\]

The left sides are now identical. Only the right sides decide what happens.

If \(\mu\ne10\), the same number \(x+2y+3z\) would have to equal two unequal numbers, \(\mu\) and \(10\). Equivalently, the subtraction equation becomes

\[
(3-3)z=\mu-10,
\]

\[
0\cdot z=\mu-10.
\]

For \(\mu\ne10\), its right side is nonzero, so this says \(0=\mu-10\ne0\), which is impossible. Therefore:

\[
\boxed{\lambda=3,\ \mu\ne10\quad\Longrightarrow\quad\text{no solution}.}
\]

If \(\mu=10\), then \(E_3\) is exactly the same equation as \(E_2\). There are only the two independent equations \(E_1\) and \(E_2\). Let the remaining free variable be \(z=t\), where \(t\) can be any real number.

From \(E_2-E_1\), as calculated above,

\[
y+2z=4.
\]

Substitute \(z=t\):

\[
y+2t=4,
\]

\[
y=4-2t.
\]

Use \(E_1\):

\[
\begin{aligned}
x+y+z&=6,\\
x+(4-2t)+t&=6,\\
x+4-2t+t&=6,\\
x+4-t&=6,\\
x&=2+t.
\end{aligned}
\]

Thus every real value of \(t\) gives a solution:

\[
(x,y,z)=(2+t,\ 4-2t,\ t).
\]

Because there are infinitely many possible values of \(t\),

\[
\boxed{\lambda=3,\ \mu=10\quad\Longrightarrow\quad\text{infinitely many solutions}.}
\]

### Final classification

| Condition | Number of solutions |
| --- | --- |
| \(\lambda\ne3\), any \(\mu\) | One unique solution |
| \(\lambda=3,\ \mu\ne10\) | No solution |
| \(\lambda=3,\ \mu=10\) | Infinitely many solutions |

**Common mistake:** when \(\lambda=3\), do not immediately call the third equation a duplicate. It is a duplicate only if its right side is also \(10\), so \(\mu=10\).

## Q5(b) Eigenvalues and corresponding eigenvectors

> Find eigen values and the corresponding eigen vectors of
>
> \[
> A=\begin{pmatrix}1&0&-1\\1&2&1\\2&2&3\end{pmatrix}.
> \]

### Underlying-concept map

An eigenvector is a nonzero input arrow for which the matrix output remains on the same line. The matrix may stretch it, shrink it, or reverse it; the scale factor is the eigenvalue. The concept note linked above explains the meaning, determinant test, and the eigenvector equation. Here the working order is:

1. Form \(A-\lambda I\) by subtracting \(\lambda\) only from the diagonal entries.
2. Calculate \(\det(A-\lambda I)\), then set it equal to zero to find the eigenvalues.
3. For each eigenvalue, solve \((A-\lambda I)\vec v=\vec0\).
4. Choose a simple nonzero free-variable value to display one eigenvector.
5. Multiply by \(A\) to check that \(A\vec v=\lambda\vec v\).

### Solve it yourself

1. Write the \(3\times3\) identity matrix and form \(A-\lambda I\).
2. Expand its determinant along the first row, using the \(+,-,+\) cofactor signs.
3. Factor the resulting cubic polynomial.
4. Substitute \(\lambda=1\), then \(2\), then \(3\), and solve each three-equation homogeneous system.

### Detailed solution

The eigenvalue condition is

\[
\det(A-\lambda I)=0.
\]

For a \(3\times3\) matrix,

\[
I=\begin{pmatrix}1&0&0\\0&1&0\\0&0&1\end{pmatrix}.
\]

Therefore

\[
\lambda I=\begin{pmatrix}\lambda&0&0\\0&\lambda&0\\0&0&\lambda\end{pmatrix},
\]

and subtracting corresponding entries gives

\[
\begin{aligned}
A-\lambda I
&=\begin{pmatrix}1&0&-1\\1&2&1\\2&2&3\end{pmatrix}
-\begin{pmatrix}\lambda&0&0\\0&\lambda&0\\0&0&\lambda\end{pmatrix}\\
&=\begin{pmatrix}1-\lambda&0&-1\\1&2-\lambda&1\\2&2&3-\lambda\end{pmatrix}.
\end{aligned}
\]

Now expand the determinant along the first row. The first-row signs are \(+,-,+\):

\[
\begin{aligned}
\det(A-\lambda I)
&=(1-\lambda)\begin{vmatrix}2-\lambda&1\\2&3-\lambda\end{vmatrix}
-0\begin{vmatrix}1&1\\2&3-\lambda\end{vmatrix}
+(-1)\begin{vmatrix}1&2-\lambda\\2&2\end{vmatrix}.
\end{aligned}
\]

Calculate each \(2\times2\) determinant using \(\begin{vmatrix}a&b\\c&d\end{vmatrix}=ad-bc\):

\[
\begin{aligned}
\begin{vmatrix}2-\lambda&1\\2&3-\lambda\end{vmatrix}
&=(2-\lambda)(3-\lambda)-(1)(2),\\
&=6-2\lambda-3\lambda+\lambda^2-2,\\
&=\lambda^2-5\lambda+4,
\end{aligned}
\]

\[
\begin{aligned}
\begin{vmatrix}1&2-\lambda\\2&2\end{vmatrix}
&=(1)(2)-(2-\lambda)(2),\\
&=2-(4-2\lambda),\\
&=2-4+2\lambda,\\
&=2\lambda-2.
\end{aligned}
\]

Substitute those results into the cofactor expansion. The middle term is zero because it is multiplied by \(0\):

\[
\begin{aligned}
\det(A-\lambda I)
&=(1-\lambda)(\lambda^2-5\lambda+4)+(-1)(2\lambda-2),\\
&=(1-\lambda)(\lambda^2-5\lambda+4)-2\lambda+2,\\
&=\lambda^2-5\lambda+4-\lambda^3+5\lambda^2-4\lambda-2\lambda+2,\\
&=-\lambda^3+6\lambda^2-11\lambda+6,\\
&=-(\lambda^3-6\lambda^2+11\lambda-6),\\
&=-(\lambda-1)(\lambda-2)(\lambda-3).
\end{aligned}
\]

Set the determinant equal to zero:

\[
-(\lambda-1)(\lambda-2)(\lambda-3)=0.
\]

A product is zero when at least one factor is zero. Hence

\[
\lambda-1=0,\qquad \lambda-2=0,\qquad \lambda-3=0,
\]

so the eigenvalues are

\[
\boxed{\lambda=1,\ 2,\ 3.}
\]

#### Eigenvector for \(\lambda=1\)

Substitute \(\lambda=1\) into \(A-\lambda I\):

\[
A-I=\begin{pmatrix}0&0&-1\\1&1&1\\2&2&2\end{pmatrix}.
\]

Let \(\vec v=\begin{pmatrix}x\\y\\z\end{pmatrix}\). The equation \((A-I)\vec v=\vec0\) gives

\[
\begin{pmatrix}0&0&-1\\1&1&1\\2&2&2\end{pmatrix}
\begin{pmatrix}x\\y\\z\end{pmatrix}
=\begin{pmatrix}0\\0\\0\end{pmatrix}.
\]

Row by row, this is

\[
-z=0,
\]

\[
x+y+z=0,
\]

\[
2x+2y+2z=0.
\]

The first equation gives \(z=0\). Substitute this into the second equation:

\[
x+y+0=0,
\]

\[
y=-x.
\]

The third equation is then automatically satisfied:

\[
2x+2(-x)+2(0)=0.
\]

Choose the free variable \(x=-t\). Then \(y=t\) and \(z=0\), so

\[
\vec v=t\begin{pmatrix}-1\\1\\0\end{pmatrix},\qquad t\ne0.
\]

One corresponding eigenvector is

\[
\boxed{\vec v_1=\begin{pmatrix}-1\\1\\0\end{pmatrix}.}
\]

Check it directly:

\[
\begin{aligned}
A\vec v_1
&=\begin{pmatrix}1&0&-1\\1&2&1\\2&2&3\end{pmatrix}
\begin{pmatrix}-1\\1\\0\end{pmatrix}\\
&=\begin{pmatrix}1(-1)+0(1)+(-1)(0)\\1(-1)+2(1)+1(0)\\2(-1)+2(1)+3(0)\end{pmatrix}\\
&=\begin{pmatrix}-1\\1\\0\end{pmatrix}\\
&=1\begin{pmatrix}-1\\1\\0\end{pmatrix}.
\end{aligned}
\]

#### Eigenvector for \(\lambda=2\)

\[
A-2I=\begin{pmatrix}-1&0&-1\\1&0&1\\2&2&1\end{pmatrix}.
\]

The equation \((A-2I)\vec v=\vec0\) gives

\[
-x-z=0,
\]

\[
x+z=0,
\]

\[
2x+2y+z=0.
\]

The first equation gives

\[
x=-z.
\]

Substitute \(x=-z\) into the third equation:

\[
2(-z)+2y+z=0,
\]

\[
-2z+2y+z=0,
\]

\[
2y-z=0,
\]

\[
2y=z,
\]

\[
y=\frac{z}{2}.
\]

Choose \(z=2t\) so that no fraction remains. Then

\[
x=-2t,
\]

\[
y=\frac{2t}{2}=t,
\]

\[
z=2t.
\]

Thus

\[
\vec v=t\begin{pmatrix}-2\\1\\2\end{pmatrix},\qquad t\ne0,
\]

and one corresponding eigenvector is

\[
\boxed{\vec v_2=\begin{pmatrix}-2\\1\\2\end{pmatrix}.}
\]

Check it:

\[
\begin{aligned}
A\vec v_2
&=\begin{pmatrix}1&0&-1\\1&2&1\\2&2&3\end{pmatrix}
\begin{pmatrix}-2\\1\\2\end{pmatrix}\\
&=\begin{pmatrix}1(-2)+0(1)+(-1)(2)\\1(-2)+2(1)+1(2)\\2(-2)+2(1)+3(2)\end{pmatrix}\\
&=\begin{pmatrix}-4\\2\\4\end{pmatrix}\\
&=2\begin{pmatrix}-2\\1\\2\end{pmatrix}.
\end{aligned}
\]

#### Eigenvector for \(\lambda=3\)

\[
A-3I=\begin{pmatrix}-2&0&-1\\1&-1&1\\2&2&0\end{pmatrix}.
\]

The equation \((A-3I)\vec v=\vec0\) gives

\[
-2x-z=0,
\]

\[
x-y+z=0,
\]

\[
2x+2y=0.
\]

The first equation gives

\[
z=-2x.
\]

The third equation gives

\[
2x+2y=0,
\]

\[
2y=-2x,
\]

\[
y=-x.
\]

Choose \(x=-t\). Then

\[
y=-(-t)=t,
\]

\[
z=-2(-t)=2t.
\]

The second equation also checks out:

\[
(-t)-t+2t=0.
\]

Therefore

\[
\vec v=t\begin{pmatrix}-1\\1\\2\end{pmatrix},\qquad t\ne0,
\]

so one corresponding eigenvector is

\[
\boxed{\vec v_3=\begin{pmatrix}-1\\1\\2\end{pmatrix}.}
\]

Check it:

\[
\begin{aligned}
A\vec v_3
&=\begin{pmatrix}1&0&-1\\1&2&1\\2&2&3\end{pmatrix}
\begin{pmatrix}-1\\1\\2\end{pmatrix}\\
&=\begin{pmatrix}1(-1)+0(1)+(-1)(2)\\1(-1)+2(1)+1(2)\\2(-1)+2(1)+3(2)\end{pmatrix}\\
&=\begin{pmatrix}-3\\3\\6\end{pmatrix}\\
&=3\begin{pmatrix}-1\\1\\2\end{pmatrix}.
\end{aligned}
\]

### Final answer

\[
\boxed{\begin{array}{c|c}
\text{Eigenvalue}&\text{A corresponding eigenvector}\\ \hline
1&\begin{pmatrix}-1\\1\\0\end{pmatrix}\\[6pt]
2&\begin{pmatrix}-2\\1\\2\end{pmatrix}\\[6pt]
3&\begin{pmatrix}-1\\1\\2\end{pmatrix}
\end{array}}
\]

Any nonzero scalar multiple of a listed eigenvector is equally valid. For example, \(\begin{pmatrix}2\\-1\\-2\end{pmatrix}\) is also an eigenvector for \(\lambda=2\), because it is \(-1\) times \(\begin{pmatrix}-2\\1\\2\end{pmatrix}\).
