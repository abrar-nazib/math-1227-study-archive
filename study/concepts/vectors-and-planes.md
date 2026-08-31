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
