# MAH pages 11–12: coplanarity and a plane

Page 11 first asks for a coplanarity proof, then starts a plane problem continued on page 12. For the base-area and height picture, read [page 10](page-10-triple-product-and-volume.md). For point-normal equations, terminal points, and the distinction between a fixed point and a general point, read [vectors and planes](../../concepts/vectors-and-planes.md). The plane question is also worked in the [2024 Q1 guide](../../2024/q1-study-guide.md).

## 1. What does coplanar mean?

Place the tails of \(\vec A,\vec B,\vec C\) together at the origin. They are **coplanar** when all three arrows lie in one plane through that origin. Picture three sticks laid flat on one tabletop: they may point in different directions, but none leaves the tabletop.

The claim is an “if and only if”: each direction needs proof.

\[
\boxed{\vec A,\vec B,\vec C\text{ coplanar}
\iff \vec A\cdot(\vec B\times\vec C)=0.}
\]

### If the vectors are coplanar, the product is zero

First suppose \(\vec B\) and \(\vec C\) are not parallel. They form the tabletop plane, and \(\vec B\times\vec C\) points perpendicular to it. Since \(\vec A\) lies on the tabletop, it is perpendicular to this normal. Hence their dot product is zero.

If \(\vec B\) and \(\vec C\) are parallel, or either is zero, their cross product is already the zero vector, so the product is again zero.

### If the product is zero, the vectors are coplanar

Again first suppose \(\vec B\) and \(\vec C\) are nonparallel. Their cross product is a nonzero normal to their plane. If its dot product with \(\vec A\) is zero, \(\vec A\) has no component along that normal, so \(\vec A\) lies in the plane spanned by \(\vec B\) and \(\vec C\).

If \(\vec B\times\vec C=\vec0\), then \(\vec B\) and \(\vec C\) are parallel or one is zero. Together with \(\vec A\), they fit in some plane through the origin. Thus this degenerate case is also coplanar.

**Correction to page 11:** for two nonzero vectors, their dot product is zero when their angle is **90°**, not 0°. At 0° they point in the same direction and their dot product is positive. A dot product is also zero if either vector is zero, in which case an angle with that zero vector is not defined.

The volume picture says the same thing: a coplanar set makes a flattened box with zero perpendicular height and hence zero volume. Be careful that the cross product is an **area vector**; its magnitude is the base area.

## 2. The plane question spanning pages 11 and 12

The notes ask for the plane perpendicular to \(\vec A=2\hat i+3\hat j+6\hat k\), passing through the terminal point of \(\vec B=\hat i+5\hat j+3\hat k\), and for the distance from the origin.

### What do we know before calculating?

Think of the plane as a flat sheet and \(\vec A\) as a pencil sticking straight through it. The pencil is a **normal vector**. Since \(\vec B\) starts at the origin, its terminal point is \(Q=(1,5,3)\), a fixed point on the sheet. Let \(P=(x,y,z)\) be any other point on that same sheet. Both points lie in the plane, so the arrow from \(P\) to \(Q\) lies in the plane and is perpendicular to the normal.

The notes use \(\overrightarrow{PQ}=\vec B-\vec r\), where \(\vec r=(x,y,z)\) is the position vector of \(P\). To see why, follow the path origin → P → Q:

\[
\begin{aligned}
\overrightarrow{OP}+\overrightarrow{PQ}&=\overrightarrow{OQ},\\
\overrightarrow{PQ}&=\overrightarrow{OQ}-\overrightarrow{OP}\\
&=(1,5,3)-(x,y,z)\\
&=(1-x,5-y,3-z).
\end{aligned}
\]

The perpendicularity condition is a zero dot product. Substitute components and expand each term:

\[
\begin{aligned}
\overrightarrow{PQ}\cdot\vec A&=0,\\
(1-x,5-y,3-z)\cdot(2,3,6)&=0,\\
2(1-x)+3(5-y)+6(3-z)&=0,\\
2-2x+15-3y+18-6z&=0,\\
35-2x-3y-6z&=0,\\
\boxed{2x+3y+6z&=35.}
\end{aligned}
\]

Check the fixed point:

\[
2(1)+3(5)+6(3)=2+15+18=35.
\]

The coefficients \((2,3,6)\) also match the required normal. Using \(\overrightarrow{QP}\) instead reverses every component, but the dot product is still zero and yields the same plane.

## 3. Distance from the origin: why a projection?

The shortest route from a point to a plane meets the plane at a right angle. Imagine walking from the origin straight toward the sheet along its normal. The vector from the origin to \(Q\) can slant sideways, but only its component along the unit normal measures that perpendicular distance.

First make the normal a unit vector:

\[
\begin{aligned}
|\vec A|&=\sqrt{2^2+3^2+6^2}\\
&=\sqrt{4+9+36}\\
&=\sqrt{49}=7,\\
\hat n&=\frac{1}{7}(2,3,6).
\end{aligned}
\]

Project the position vector of \(Q\) onto this unit normal. The signed scalar projection can be negative for a different orientation, so take its absolute value to get distance:

\[
\begin{aligned}
d&=|\vec B\cdot\hat n|\\
&=\left|(1,5,3)\cdot\frac{1}{7}(2,3,6)\right|\\
&=\left|\frac{1}{7}(1(2)+5(3)+3(6))\right|\\
&=\left|\frac{2+15+18}{7}\right|\\
&=\boxed{5\text{ units}.}
\end{aligned}
\]

The handwritten numerator in the projection line appears to show a coefficient of 5 on \(\hat k\); the given normal, denominator, and next line all require **6**. The result 5 is correct with that correction. Also, the dot product shown is a scalar projection; a vector projection would have a direction as well.

As an independent check, the point-to-plane distance formula for \(ax+by+cz+d_0=0\) and a point \((x_0,y_0,z_0)\) is

\[
D=\frac{|ax_0+by_0+cz_0+d_0|}{\sqrt{a^2+b^2+c^2}}.
\]

Here \(a=2,b=3,c=6,d_0=-35\), and the point is \((0,0,0)\):

\[
\begin{aligned}
D&=\frac{|2(0)+3(0)+6(0)-35|}{\sqrt{2^2+3^2+6^2}}\\
&=\frac{|-35|}{\sqrt{4+9+36}}\\
&=\frac{35}{7}\\
&=5.
\end{aligned}
\]
