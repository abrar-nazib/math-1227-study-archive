# Vectors and Planes

## 1. Vectors: direction and magnitude

A vector in three dimensions is written as

\[
\vec v=a\hat i+b\hat j+c\hat k=\langle a,b,c\rangle.
\]

It describes a direction and a size. For example, \(\langle2,3,6\rangle\) points 2 units in the \(x\)-direction, 3 in the \(y\)-direction, and 6 in the \(z\)-direction. Its length is

\[
|\vec v|=\sqrt{a^2+b^2+c^2}.
\]

For a plane problem, the important feature is usually the **direction**, not this length.

## 2. Normal vectors and perpendicularity

A vector \(\vec n\) is a **normal vector** to a plane when it is perpendicular to every direction lying in that plane. A plane is therefore determined by:

- one point \(P_0(x_0,y_0,z_0)\) on it, and
- one non-zero normal vector \(\vec n=\langle a,b,c\rangle\).

The key translation is:

> “The plane is perpendicular to \(\vec v\)” means that \(\vec v\) is a normal vector of the plane.

This is a frequent source of confusion. The vector is not a direction *along* the plane; it points straight out of it.

### How perpendicularity is measured

For two non-zero vectors \(\vec u\) and \(\vec v\), their dot product satisfies

\[
\vec u\cdot\vec v=|\vec u|\,|\vec v|\cos\theta,
\]

where \(\theta\) is the angle between them. They are perpendicular exactly when \(\theta=90^\circ\). Since \(\cos90^\circ=0\), the practical test is

\[
\boxed{\vec u\cdot\vec v=0.}
\]

For example, \(\langle2,3,6\rangle\cdot\langle3,-2,0\rangle=6-6+0=0\), so these two vectors are perpendicular. We do not usually measure a plane's perpendicularity by one numerical angle: a plane is perpendicular to a vector when that vector is perpendicular to **every** direction lying in the plane. Such a vector is the plane's normal.

## 3. The point-normal equation of a plane

Let \(P_0(x_0,y_0,z_0)\) be one fixed, known point on the required plane, and let \(P(x,y,z)\) be any other point on that same plane. The coordinates of \(P\) are variables: the equation below selects exactly those values of \(P\) that lie on the plane. The displacement from \(P_0\) to \(P\) is

\[
\overrightarrow{P_0P}=\langle x-x_0,y-y_0,z-z_0\rangle.
\]

Because this displacement lies in the plane, it must be perpendicular to the normal \(\vec n\). Thus

> [!IMPORTANT]
> **Exam formula — point-normal form**

\[
\vec n\cdot\overrightarrow{P_0P}=0.
\]

If \(\vec n=\langle a,b,c\rangle\), this becomes

> [!IMPORTANT]
> **Exam formula — plane through \(P_0(x_0,y_0,z_0)\) with normal \(\langle a,b,c\rangle\)**

\[
a(x-x_0)+b(y-y_0)+c(z-z_0)=0.
\]

### Example

Find the plane perpendicular to \(\langle1,-2,3\rangle\) through \((2,1,-1)\).

Use the vector as the normal:

\[
1(x-2)-2(y-1)+3(z+1)=0.
\]

Expanding gives \(x-2y+3z+3=0\). Both forms describe exactly the same plane; the point-normal form is usually safer while working.

## 4. Terminal point of a vector

An arrow representing a vector has two endpoints:

- the **initial point** (or tail/base), where the arrow starts;
- the **terminal point** (or head), where the arrow points.

So the terminal point is the **arrow head**, not the arrow base. When a vector \(\langle p,q,r\rangle\) is drawn from the origin, it starts at \((0,0,0)\) and its terminal point is \((p,q,r)\). So the terminal point of

\[
\hat i+5\hat j+3\hat k
\]

is simply \((1,5,3)\). There is no extra calculation.

If a vector is drawn from another initial point \(P(x_0,y_0,z_0)\), add its components to \(P\). For instance, a vector \(\langle2,-1,4\rangle\) starting at \((1,3,2)\) ends at \((3,2,6)\).

## 5. Self-check

After finding a plane, check both facts:

1. Substitute the given point. The left-hand side must be zero.
2. The coefficients of \(x,y,z\) must be proportional to the given perpendicular vector.

## 6. Linear independence of vectors

Vectors are **linearly independent** when none of them can be built by combining the others. Think of each vector as a genuinely new direction of movement. Three independent vectors in three-dimensional space give three distinct directions; if one can be assembled from the other two, it adds no new direction and the set is dependent.

To test vectors \(\vec A,\vec B,\vec C\), ask whether

> [!IMPORTANT]
> **Exam test — linear independence**
>
> \[
> a\vec A+b\vec B+c\vec C=\vec0
> \]
>
> has only the **trivial solution** \(a=b=c=0\). If it does, the vectors are independent. Any nontrivial solution gives a dependent relation.

Put the vectors as columns of a square matrix. For three vectors in \(\mathbb R^3\), a nonzero determinant is the fast test:

> [!IMPORTANT]
> **Exam test — determinant shortcut in \(\mathbb R^3\)**
>
> \[
> \det[\vec A\ \vec B\ \vec C]\ne0
> \quad\Longrightarrow\quad
> \vec A,\vec B,\vec C\text{ are linearly independent.}
> \]

If the determinant is zero, the vectors are dependent; solve \(a\vec A+b\vec B+c\vec C=\vec0\) to find the requested relation.

### Reading the MAH notes, page 6: why the four vectors are dependent

Page 6 of **Math MAH Notes** gives the vectors

\[
\begin{aligned}
\vec r_1&=2\hat i-\hat j+\hat k,\\
\vec r_2&=\hat i+3\hat j-2\hat k,\\
\vec r_3&=-2\hat i+\hat j-3\hat k,\\
\vec r_4&=3\hat i+2\hat j+5\hat k.
\end{aligned}
\]

The page is testing one simple idea: can \(\vec r_4\) be made by mixing the first three arrows? If it can, it gives no new direction. The set is then linearly dependent.

The notes write this as

\[
\vec r_4=\alpha_1\vec r_1+\alpha_2\vec r_2+\alpha_3\vec r_3.
\]

Here \(\alpha_1,\alpha_2,\alpha_3\) are ordinary numbers, called **scalars**. Think of them as knobs: each knob says how much to stretch a vector, and a negative setting reverses it.

Substitute the component forms, without combining anything yet:

\[
\begin{aligned}
3\hat i+2\hat j+5\hat k
&=\alpha_1(2\hat i-\hat j+\hat k)
+\alpha_2(\hat i+3\hat j-2\hat k)
+\alpha_3(-2\hat i+\hat j-3\hat k).
\end{aligned}
\]

Now collect the \(\hat i\), \(\hat j\), and \(\hat k\) parts separately:

\[
\begin{aligned}
3\hat i+2\hat j+5\hat k
={}&(2\alpha_1+\alpha_2-2\alpha_3)\hat i\\
&+(-\alpha_1+3\alpha_2+\alpha_3)\hat j\\
&+(\alpha_1-2\alpha_2-3\alpha_3)\hat k.
\end{aligned}
\]

The vectors \(\hat i\), \(\hat j\), and \(\hat k\) point in three independent coordinate directions. Therefore two vectors written in this basis are equal only when their matching components are equal. This is what the handwritten note means by “\(\hat i,\hat j,\hat k\) are non-coplanar.” Equate the three components:

\[
\begin{aligned}
2\alpha_1+\alpha_2-2\alpha_3&=3,\\
-\alpha_1+3\alpha_2+\alpha_3&=2,\\
\alpha_1-2\alpha_2-3\alpha_3&=5.
\end{aligned}
\]

### How are the scalars found?

They are found by solving those three simultaneous equations. The handwritten notes skip that calculation; the values are not chosen by intuition. Let us eliminate one unknown at a time.

Add the second equation to the third. Their \(\alpha_1\) terms cancel:

\[
\begin{aligned}
(-\alpha_1+3\alpha_2+\alpha_3)
+(\alpha_1-2\alpha_2-3\alpha_3)&=2+5,\\
\alpha_2-2\alpha_3&=7. \tag{4}
\end{aligned}
\]

Add twice the second equation to the first. Again \(\alpha_1\) cancels:

\[
\begin{aligned}
(2\alpha_1+\alpha_2-2\alpha_3)
+2(-\alpha_1+3\alpha_2+\alpha_3)&=3+2(2),\\
2\alpha_1+\alpha_2-2\alpha_3-2\alpha_1+6\alpha_2+2\alpha_3&=7,\\
7\alpha_2&=7,\\
\alpha_2&=1.
\end{aligned}
\]

Substitute \(\alpha_2=1\) into equation (4):

\[
\begin{aligned}
1-2\alpha_3&=7,\\
-2\alpha_3&=6,\\
\alpha_3&=-3.
\end{aligned}
\]

Finally substitute both values into the third original equation:

\[
\begin{aligned}
\alpha_1-2(1)-3(-3)&=5,\\
\alpha_1-2+9&=5,\\
\alpha_1+7&=5,\\
\alpha_1&=-2.
\end{aligned}
\]

Thus the scalars in the notes are

\[
\alpha_1=-2,\qquad \alpha_2=1,\qquad \alpha_3=-3.
\]

Check each coordinate, rather than merely trusting the solved values:

\[
\begin{aligned}
2\alpha_1+\alpha_2-2\alpha_3
&=2(-2)+1-2(-3)\\
&=-4+1+6\\
&=3,\\[4pt]
-\alpha_1+3\alpha_2+\alpha_3
&=-(-2)+3(1)+(-3)\\
&=2+3-3\\
&=2,\\[4pt]
\alpha_1-2\alpha_2-3\alpha_3
&=-2-2(1)-3(-3)\\
&=-2-2+9\\
&=5.
\end{aligned}
\]

So the complete relation is

> [!IMPORTANT]
> **MAH page 6 result**
>
> \[
> \vec r_4=-2\vec r_1+\vec r_2-3\vec r_3.
> \]

That one equation is enough to settle the question: \(\vec r_4\) can be assembled from the other three vectors, so the four vectors are **linearly dependent**. Written in the formal “combination equals zero” test, move everything to one side:

\[
2\vec r_1-\vec r_2+3\vec r_3+\vec r_4=\vec0.
\]

The coefficients \(2,-1,3,1\) are not all zero. That is exactly the required evidence of linear dependence.

### A small correction to the top diagram on that page

The determinant statement is correct when \(\vec A,\vec B,\vec C\) are the **position vectors from the origin**:

\[
\det\begin{pmatrix}
a_1&a_2&a_3\\
b_1&b_2&b_3\\
c_1&c_2&c_3
\end{pmatrix}=0
\]

means the three vectors are linearly dependent, equivalently they lie in one plane **through the origin**. The phrase “the points \(A,B,C\) are coplanar” by itself is not useful here: any three ordinary points always lie in at least one plane. What matters is that their position vectors and the origin lie in one common plane.
