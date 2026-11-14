# MAH page 10: triple products and volume

The page explains how three vectors determine the volume of a slanted box and of a triangular pyramid. Read [cross-product components](../../concepts/curl-surface-and-volume-integrals.md#from-two-surface-directions-to-a-normal) as a reference; the idea of a dot product selecting a component normal to a surface also appears in [the flux explanation](../../concepts/curl-surface-and-volume-integrals.md#3-surface-flux-what-passes-through-a-sheet). The construction here is new: we combine both operations to measure a solid's volume.

## Picture the box first

Imagine a shoebox made from flexible cardboard, tilted sideways. Its base is a parallelogram. Tilting an edge sideways does not change the perpendicular height if its vertical component stays fixed. To find the space inside, multiply the base area by the **perpendicular** height—not by the length of a slanted edge.

Let three vectors \(\vec A,\vec B,\vec C\) start at the same corner. Use \(\vec B,\vec C\) as the two base edges and \(\vec A\) as the slanted rising edge. Assume first that the base edges are not parallel, so they make a genuine plane.

The cross product \(\vec B\times\vec C\) points perpendicular to the base. Its **magnitude**, rather than the vector itself, is the base area:

\[
\text{base area}=|\vec B\times\vec C|.
\]

Write \(\hat n=(\vec B\times\vec C)/|\vec B\times\vec C|\) for a unit normal, an arrow of length one perpendicular to the base. Let \(\theta\) be the angle between \(\vec A\) and \(\hat n\). The signed component of the slanted edge in that normal direction is

\[
\vec A\cdot\hat n=|\vec A|\cos\theta.
\]

The actual perpendicular height is nonnegative, so it is \(|\vec A\cdot\hat n|\). Multiplying base area by height gives

\[
\begin{aligned}
V&=|\vec B\times\vec C|\,|\vec A\cdot\hat n|\\
&=\left|\vec A\cdot\bigl(|\vec B\times\vec C|\hat n\bigr)\right|\\
&=\boxed{|\vec A\cdot(\vec B\times\vec C)|}.
\end{aligned}
\]

The expression inside the absolute value is called the **scalar triple product**: first take a cross product of two vectors, then a dot product with the third. The output is a number, possibly negative. Its sign records orientation; ordinary physical volume is its absolute value. Page 10 omits that absolute value in its final equality, which is only valid as written when the chosen orientation gives a nonnegative result. If the base edges are parallel, their cross product is zero and the volume is zero too; no unit normal need be chosen.

### A concrete calculation

Take

\[
\vec B=(2,0,0),\quad \vec C=(0,3,0),\quad \vec A=(1,1,4).
\]

The base edges point along the two horizontal axes, with lengths 2 and 3. The rising edge is slanted, but rises 4 units. Using the component cross-product formula:

\[
\begin{aligned}
\vec B\times\vec C
&=(0\cdot0-0\cdot3,\ 0\cdot0-2\cdot0,\ 2\cdot3-0\cdot0)\\
&=(0,0,6),\\
\vec A\cdot(\vec B\times\vec C)
&=(1,1,4)\cdot(0,0,6)\\
&=1(0)+1(0)+4(6)\\
&=24.
\end{aligned}
\]

Thus the volume is \(|24|=24\) cubic units, matching base area \(2\times3=6\) times height \(4\). Reversing the order of the two base vectors changes the triple product to \(-24\), but the volume remains \(24\).

## Tetrahedron: where does one sixth come from?

A tetrahedron is a triangular pyramid. Take three edges \(\vec a,\vec b,\vec c\) from one common vertex; choose \(\vec a,\vec b\) for the triangular base. Its base is half the corresponding parallelogram, so

\[
\text{triangle base area}=\tfrac12|\vec a\times\vec b|.
\]

A pyramid's volume is one third of its base area times its perpendicular height. If \(\hat n\) is a unit normal to a nondegenerate base, the height is \(|\vec c\cdot\hat n|\). Therefore

\[
\begin{aligned}
V_{\text{tetrahedron}}
&=\tfrac13\left(\tfrac12|\vec a\times\vec b|\right)|\vec c\cdot\hat n|\\
&=\tfrac16\left|\vec c\cdot(\vec a\times\vec b)\right|\\
&=\boxed{\tfrac16\left|\vec a\cdot(\vec b\times\vec c)\right|}.
\end{aligned}
\]

The factor \(1/2\) comes from the triangular base; the factor \(1/3\) comes from the pyramid-volume formula. For the box example above, the tetrahedron formed from the same three edges has volume \(24/6=4\). For a degenerate base the volume is zero.

## Changing the order

The page's cyclic identity is

\[
\vec a\cdot(\vec b\times\vec c)
=\vec b\cdot(\vec c\times\vec a)
=\vec c\cdot(\vec a\times\vec b).
\]

These are cyclic rotations: the order \(a,b,c\) is kept as the starting point moves. Swapping two vectors instead reverses the sign. The absolute volume stays the same either way.
