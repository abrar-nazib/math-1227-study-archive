# Math 1227 — 2022 Q1 study guide

Read [Vectors and planes](../concepts/vectors-and-planes.md) for unit vectors and dot products, and [Scalar fields, gradients, and potentials](../concepts/scalar-fields-gradient-and-potential.md) for parts (b) and (c).

## Q1(a) Work done by two forces

> Forces of magnitudes 5 and 3 units acting in the direction \(6\hat i+2\hat j+3\hat k\) and \(3\hat i-2\hat j+6\hat k\) respectively act on a particle which is displaced from the point \((2,2,-1)\) to \((4,3,1)\). Find the work done by the forces.

The displacement is final point minus initial point:

\[
\vec d=\langle4-2,3-2,1-(-1)\rangle=\langle2,1,2\rangle.
\]

Both given direction vectors have length

\[
\sqrt{6^2+2^2+3^2}=\sqrt{49}=7,
\qquad
\sqrt{3^2+(-2)^2+6^2}=\sqrt{49}=7.
\]

Thus the actual force vectors are magnitude times unit direction:

\[
\vec F_1=5\left\langle\frac67,\frac27,\frac37\right\rangle
=\left\langle\frac{30}7,\frac{10}7,\frac{15}7\right\rangle,
\]

\[
\vec F_2=3\left\langle\frac37,\frac{-2}7,\frac67\right\rangle
=\left\langle\frac97,\frac{-6}7,\frac{18}7\right\rangle.
\]

\[
\vec F=\vec F_1+\vec F_2
=\left\langle\frac{39}7,\frac47,\frac{33}7\right\rangle.
\]

> [!IMPORTANT]
> **Exam formula — work by a constant force**
>
> \[
> W=\vec F\cdot\vec d.
> \]

\[
W=\left\langle\frac{39}7,\frac47,\frac{33}7\right\rangle\cdot\langle2,1,2\rangle.
\]

\[
=\frac{39}7(2)+\frac47(1)+\frac{33}7(2).
\]

\[
=\boxed{\frac{148}{7}\text{ units of work}}.
\]

## Q1(b) Direction of greatest increase

> In what direction from the point \((1,3,2)\) is the directional derivative of \(\phi=2xz-y^2\) a maximum? What is the magnitude of this maximum?

The gradient points in the direction in which a scalar field rises most steeply:

\[
\nabla\phi=
\left\langle\frac{\partial\phi}{\partial x},\frac{\partial\phi}{\partial y},\frac{\partial\phi}{\partial z}\right\rangle.
\]

Holding the other variables fixed,

\[
\frac{\partial\phi}{\partial x}=2z,\qquad
\frac{\partial\phi}{\partial y}=-2y,\qquad
\frac{\partial\phi}{\partial z}=2x.
\]

\[
\nabla\phi=\langle2z,-2y,2x\rangle.
\]

At \((1,3,2)\),

\[
\nabla\phi(1,3,2)=\langle4,-6,2\rangle.
\]

Its magnitude is

\[
\left\lVert\nabla\phi\right\rVert
=\sqrt{4^2+(-6)^2+2^2}
=\sqrt{56}
=2\sqrt{14}.
\]

The required direction is the unit gradient:

\[
\frac{\nabla\phi}{\lVert\nabla\phi\rVert}
=\frac{\langle4,-6,2\rangle}{2\sqrt{14}}
=\boxed{\frac{\langle2,-3,1\rangle}{\sqrt{14}}}.
\]

The maximum directional derivative is

\[
\boxed{2\sqrt{14}}.
\]

## Q1(c) Conservative field and scalar potential

> Show that \(\vec F=(2xy+z^3)\hat i+x^2\hat j+3xz^2\hat k\) is a conservative force field. Also, find the scalar potential.

Write

\[
P=2xy+z^3,\qquad Q=x^2,\qquad R=3xz^2.
\]

Calculate curl:

\[
\nabla\times\vec F
=\left\langle R_y-Q_z,\ P_z-R_x,\ Q_x-P_y\right\rangle.
\]

\[
R_y=0,\qquad Q_z=0,
\]

\[
P_z=3z^2,\qquad R_x=3z^2,
\]

\[
Q_x=2x,\qquad P_y=2x.
\]

\[
\nabla\times\vec F=\langle0-0,3z^2-3z^2,2x-2x\rangle
=\langle0,0,0\rangle.
\]

The field is defined throughout all space, so zero curl proves it is conservative.

For a potential \(\phi\), require \(\nabla\phi=\vec F\). Start with \(\phi_x=P\):

\[
\phi=\int(2xy+z^3)\,dx+g(y,z).
\]

[Power rule: \(\int x^n\,dx=x^{n+1}/(n+1)+C\); \(y,z\) are constant during this integration.]

\[
\phi=x^2y+xz^3+g(y,z).
\]

Differentiate with respect to \(y\):

\[
\phi_y=x^2+g_y(y,z).
\]

Match \(\phi_y=Q=x^2\):

\[
x^2+g_y=x^2,
\qquad
g_y=0.
\]

Thus \(g\) has no \(y\)-dependence, so write \(g=h(z)\). Differentiate with respect to \(z\):

\[
\phi_z=3xz^2+h'(z).
\]

Match \(\phi_z=R=3xz^2\):

\[
3xz^2+h'(z)=3xz^2,
\qquad
h'(z)=0.
\]

\[
\boxed{\phi(x,y,z)=x^2y+xz^3+C.}
\]
