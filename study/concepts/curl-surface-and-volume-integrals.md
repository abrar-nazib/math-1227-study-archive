# Curl, Surface Integrals, and Volume Integrals

This note supplies the background needed for 2024 Q2. Read the sections in order: each later operation uses the earlier ones.

## 1. Concept map

There are two questions in 2024 Q2, and each asks for a different kind of accumulation.

| Question | Object being accumulated | Region | Result |
| --- | --- | --- | --- |
| Q2(a) | The component of curl passing through a surface | A finite piece of a plane | One number (a scalar) |
| Q2(b) | The curl vector at every point | A three-dimensional solid | One vector |

Both begin by finding the **curl** of a vector field. After that, Q2(a) needs a surface parameterization and Q2(b) needs three-dimensional integration limits.

## 2. Partial derivatives: changing one input at a time

A function such as \(f(x,y,z)\) has three inputs. A partial derivative asks how the function changes when only one input changes and the other two are temporarily treated as constants. The symbol after \(\partial\) tells you which input is allowed to vary.

For example, when differentiating with respect to \(y\), the symbols \(x\) and \(z\) are constants:

\[
\begin{aligned}
\frac{\partial(x+2y-3z)}{\partial y}
&=\frac{\partial x}{\partial y}+\frac{\partial(2y)}{\partial y}-\frac{\partial(3z)}{\partial y}\\
&=0+2-0\\
&=2.
\end{aligned}
\]

> [!IMPORTANT]
> **Exam formulas — basic partial derivatives**

\[
\frac{\partial x}{\partial x}=1,\qquad
\frac{\partial y}{\partial y}=1,\qquad
\frac{\partial z}{\partial z}=1,
\]

\[
\frac{\partial x}{\partial y}=0,\qquad
\frac{\partial x}{\partial z}=0,\qquad
\frac{\partial y}{\partial x}=0,
\]

and, for a constant \(c\),

\[
\frac{\partial(cu)}{\partial u}=c,
\qquad
\frac{\partial c}{\partial u}=0.
\]

The ordinary power rule is used in exactly the same way for the variable that is changing:

\[
\frac{\partial(x^n)}{\partial x}=nx^{n-1}.
\]

## 3. Curl: the local turning tendency of a vector field

A vector field assigns an arrow to every position. Curl describes the field's local tendency to make a tiny paddle wheel turn. It is itself a vector: its direction gives the turning axis, and its size measures the strength of that local turning.

Write a vector field as

\[
\vec F=P\hat i+Q\hat j+R\hat k,
\]

where \(P,Q,R\) are the \(x\)-, \(y\)-, and \(z\)-components. The symbol \(\nabla\) is read “del.” For calculation, use this component formula rather than trying to remember the determinant layout.

> [!IMPORTANT]
> **Exam formula — curl in component form**

\[
\nabla\times\vec F=
\left(\frac{\partial R}{\partial y}-\frac{\partial Q}{\partial z}\right)\hat i
+\left(\frac{\partial P}{\partial z}-\frac{\partial R}{\partial x}\right)\hat j
+\left(\frac{\partial Q}{\partial x}-\frac{\partial P}{\partial y}\right)\hat k.
\]

### A careful mini-example

Let

\[
\vec G=y\hat i+2x\hat j+0\hat k.
\]

Thus \(P=y\), \(Q=2x\), and \(R=0\). Substitute these three components into the formula one component at a time:

\[
\begin{aligned}
\nabla\times\vec G
&=\left(\frac{\partial 0}{\partial y}-\frac{\partial (2x)}{\partial z}\right)\hat i
+\left(\frac{\partial y}{\partial z}-\frac{\partial 0}{\partial x}\right)\hat j
+\left(\frac{\partial (2x)}{\partial x}-\frac{\partial y}{\partial y}\right)\hat k\\
&=(0-0)\hat i+(0-0)\hat j+(2-1)\hat k\\
&=\hat k.
\end{aligned}
\]

The result points in the positive \(z\)-direction, so the tiny paddle wheel would turn about a vertical axis.

## 4. Surface, normal direction, and flux

A **surface** is a two-dimensional sheet in space. At each point of a smooth surface, a **normal vector** points straight out of the sheet. A vector field can have a component through the sheet and a component sliding along it. A flux integral counts only the component that passes through it.

For a constant vector \(\vec C\) crossing a flat rectangular sheet, the central idea is

\[
(\text{component of \(\vec C\) normal to the sheet})\times(\text{area of the sheet}).
\]

The dot product performs the “normal component” part. The surface integral adds that quantity over every tiny patch of a curved or slanted surface.

> [!IMPORTANT]
> **Exam formula — flux of a vector field through an oriented surface**

\[
\iint_S\vec C\cdot\hat n\,dS.
\]

Here \(\hat n\) is a unit normal, \(dS\) is a tiny positive area, and the pair \(\hat n\,dS\) records a tiny **oriented area vector**. Reversing the normal reverses the sign of the answer.

### Why a parameterization replaces \(\hat n\,dS\)

Describe a surface using two independent variables \(u\) and \(v\):

\[
\vec r(u,v)=\langle x(u,v),y(u,v),z(u,v)\rangle.
\]

Changing \(u\) while holding \(v\) fixed gives one tangent vector \(\vec r_u\). Changing \(v\) while holding \(u\) fixed gives another tangent vector \(\vec r_v\). Their cross product is perpendicular to both tangents, so it is normal to the surface. Its length automatically gives the area-scaling factor.

> [!IMPORTANT]
> **Exam formula — parameterized surface flux**

\[
\iint_S\vec C\cdot\hat n\,dS
=\iint_D\vec C(\vec r(u,v))\cdot(\vec r_u\times\vec r_v)\,du\,dv.
\]

The order of the cross product selects an orientation. Using \(\vec r_v\times\vec r_u\) instead gives the negative vector and therefore the negative flux.

## 5. Turning a plane equation into a surface parameterization

Suppose a plane is written as

\[
Ax+By+Cz=D,
\]

with \(C\ne0\). Solve for \(z\):

> [!IMPORTANT]
> **Exam formula — plane written as a graph**

\[
z=\frac{D-Ax-By}{C}.
\]

Now use \(x\) and \(y\) themselves as the two parameters:

> [!IMPORTANT]
> **Exam formula — parameterization of \(z=f(x,y)\)**

\[
\vec r(x,y)=\langle x,y,f(x,y)\rangle.
\]

For this choice, \(\vec r_x\times\vec r_y\) has a positive \(z\)-component. It is the upward orientation. The opposite orientation is its negative.

### Mini-example: a sloping plane

For the plane \(x+y+z=3\), solve for \(z\):

\[
\begin{aligned}
x+y+z&=3,\\
z&=3-x-y.
\end{aligned}
\]

Parameterize it:

\[
\vec r(x,y)=\langle x,y,3-x-y\rangle.
\]

Differentiate each component:

\[
\begin{aligned}
\vec r_x
&=\left\langle\frac{\partial x}{\partial x},\frac{\partial y}{\partial x},\frac{\partial(3-x-y)}{\partial x}\right\rangle
=\langle1,0,-1\rangle,\\
\vec r_y
&=\left\langle\frac{\partial x}{\partial y},\frac{\partial y}{\partial y},\frac{\partial(3-x-y)}{\partial y}\right\rangle
=\langle0,1,-1\rangle.
\end{aligned}
\]

Then

\[
\begin{aligned}
\vec r_x\times\vec r_y
&=\begin{vmatrix}
\hat i&\hat j&\hat k\\
1&0&-1\\
0&1&-1
\end{vmatrix}\\
&=\big[0(-1)-(-1)(1)\big]\hat i
-\big[1(-1)-(-1)(0)\big]\hat j
+\big[1(1)-0(0)\big]\hat k\\
&=\hat i+\hat j+\hat k.
\end{aligned}
\]

Its positive \(z\)-component confirms that this is the upward normal direction.

## 6. Triple integrals of a vector field

A triple integral adds a quantity through a solid region \(V\). If the integrand is a vector, integrate each component separately:

> [!IMPORTANT]
> **Exam formula — triple integral of a vector field**

\[
\iiint_V\langle A,B,C\rangle\,dV
=\left\langle\iiint_V A\,dV,\iiint_V B\,dV,\iiint_V C\,dV\right\rangle.
\]

The notation \(dV\) means a tiny volume. In Cartesian coordinates, \(dV=dz\,dy\,dx\) means: first add along \(z\), then along \(y\), then along \(x\). The order may be changed, but the bounds must match the chosen order.

## 7. Reading the bounds of a tetrahedral region

The coordinate planes \(x=0\), \(y=0\), and \(z=0\), together with a sloping plane, enclose a corner-shaped solid called a tetrahedral region.

For example, take

\[
2x+2y+z=4.
\]

First solve the sloping plane for the vertical coordinate \(z\):

\[
\begin{aligned}
2x+2y+z&=4,\\
z&=4-2x-2y.
\end{aligned}
\]

At a fixed allowed \((x,y)\), the solid starts at the bottom plane \(z=0\) and ends at that sloping plane:

\[
0\le z\le4-2x-2y.
\]

For this upper bound to be non-negative,

\[
\begin{aligned}
4-2x-2y&\ge0,\\
4&\ge2x+2y,\\
2&\ge x+y,\\
y&\le2-x.
\end{aligned}
\]

The conditions \(x\ge0\) and \(y\ge0\) come from the coordinate planes. In the \(xy\)-plane, the projection is therefore the triangle bounded by \(x=0\), \(y=0\), and \(x+y=2\). Taking \(x\) as the outside variable gives

> [!IMPORTANT]
> **Exam formula — bounds for this tetrahedral region**

\[
0\le x\le2,\qquad 0\le y\le2-x,\qquad 0\le z\le4-2x-2y.
\]

Thus an integral over this solid can be written as

\[
\int_0^2\int_0^{2-x}\int_0^{4-2x-2y}(\text{integrand})\,dz\,dy\,dx.
\]

## 8. Exam checklist for 2024 Q2

For Q2(a): find curl; solve the plane for \(z\); parameterize it; calculate both tangent vectors and their cross product; make the chosen orientation explicit; substitute into the flux integral.

For Q2(b): find curl; solve the top plane for \(z\); derive the triangular \(xy\)-projection rather than guessing it; integrate every component over the same bounds; assemble the three answers as one vector.
