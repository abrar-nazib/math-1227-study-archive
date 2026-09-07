# Scalar Fields, Gradients, and Potential Functions

## 1. Scalar field versus vector field

Start with an ordinary function: it takes an input and returns an output. A **field** is a function whose input is a location in space. It is not an extra physical object; it is a rule or map spread across a region that answers this question:

> “If I stand at this particular location, what value or arrow belongs here?”

Imagine a map of a room drawn on graph paper. At every square, you could write the room's temperature. The complete collection of those values—one for every location—is the temperature field. You do not need to write every value separately; the formula \(T(x,y,z)\) is a compact rule that generates them all.

For example, \(T(x,y)=20+x\) says: move one unit in the positive \(x\)-direction and the temperature reading increases by 1. At \((0,0)\) the reading is 20; at \((3,0)\) it is 23. That location-to-information rule is what “field” means.

The key question is: **what kind of output does the field give?**

| Field type | Output at each point | A physical picture |
| --- | --- | --- |
| Scalar field | One number | Temperature, altitude, pressure |
| Vector field | A vector: size and direction | Wind velocity, force, fluid flow |

### Scalar field: one value at each location

A **scalar** is just a number, with no direction. For instance, if

\[
T(x,y,z)=20+x-2y,
\]

then \(T\) is a scalar field. At the point \((2,1,0)\),

\[
T(2,1,0)=20+2-2(1)=20.
\]

That result means “the temperature at this location is 20” (in whichever temperature unit is being used). It does **not** point anywhere. Imagine a weather map whose every location has one temperature written on it: that is a scalar field.

### Vector field: an arrow at each location

A **vector** has magnitude and direction. A vector field attaches one arrow to every point. For example,

\[
\vec F(x,y,z)=P\hat i+Q\hat j+R\hat k.
\]

If \(\vec F(2,1,0)=3\hat i-\hat j\), the field says that at \((2,1,0)\), the arrow points 3 units in the positive \(x\)-direction and 1 unit in the negative \(y\)-direction. If \(\vec F\) is a force field, this is the force a particle would feel at that location. If it is a wind field, this is the wind velocity there.

The field does not move by itself; it is a rule that tells you which arrow to draw **after** choosing a location.

### The connection: gradient

The gradient operator turns a scalar field \(\phi\) into a vector field:

> [!IMPORTANT]
> **Exam formula — gradient of a scalar field**

\[
\nabla\phi=\frac{\partial\phi}{\partial x}\hat i+
\frac{\partial\phi}{\partial y}\hat j+
\frac{\partial\phi}{\partial z}\hat k.
\]

Geometrically, \(\nabla\phi\) points in the direction where \(\phi\) increases most rapidly.

For a simple example, let \(\phi(x,y)=x^2+y^2\). This scalar field gives the number \(x^2+y^2\) at each point. Its gradient is

\[
\nabla\phi=2x\hat i+2y\hat j.
\]

At \((1,2)\), the gradient is \(2\hat i+4\hat j\): an arrow pointing away from the origin. It tells us the quickest direction in which the values of \(x^2+y^2\) rise.

### Geometrical interpretation: steepest rise and level surfaces

Fix one value \(c\). The set of points where \(\phi(x,y,z)=c\) is a **level surface**: every point on it has the same scalar-field reading. For temperature, it is an imaginary sheet joining all points with the same temperature; for altitude, it is a contour surface of equal height.

If you walk a tiny distance \(d\vec r\) *along* a level surface, the reading does not change, so \(d\phi=0\). The differential relation is

> [!IMPORTANT]
> **Exam formula — geometric meaning of the gradient**
>
> \[
> d\phi=\nabla\phi\cdot d\vec r.
> \]
>
> Along a level surface, \(d\phi=0\), so \(\nabla\phi\) is perpendicular to every tangent direction \(d\vec r\). Therefore \(\nabla\phi\) is normal to the level surface \(\phi=c\).

The dot product also explains “steepest.” If \(\hat u\) is a unit direction, the rate of change of \(\phi\) in that direction is \(\nabla\phi\cdot\hat u\). This is largest when \(\hat u\) points in exactly the same direction as \(\nabla\phi\). The largest rate is \(|\nabla\phi|\).

> [!IMPORTANT]
> **Exam interpretation of \(\nabla\phi\)**
>
> \(\nabla\phi\) points in the direction of maximum increase of \(\phi\); \(|\nabla\phi|\) is that maximum rate of increase; and \(\nabla\phi\) is normal to the level surface \(\phi=c\).

For \(\phi=x^2+y^2+z^2\), the level surfaces \(\phi=c\) are spheres centered at the origin. Its gradient \(\nabla\phi=2x\hat i+2y\hat j+2z\hat k\) points directly outward, which is perpendicular to a sphere and is the direction in which distance from the origin increases fastest.

### A quick recognition test

- If the output is a single expression such as \(\phi=x^2+y^2+z^2\), it is a scalar field.
- If the output has \(\hat i,\hat j,\hat k\) components, such as \(\vec F=x\hat i+y\hat j+z\hat k\), it is a vector field.
- \(\nabla\phi\) starts with a scalar field and produces a vector field.

## 2. Conservative fields and potentials

A vector field is **conservative** when it comes from a scalar potential. Depending on the convention, one writes either

> [!IMPORTANT]
> **Exam formula — conservative field and potential**

\[
\vec F=\nabla f \qquad\text{or}\qquad \vec F=-\nabla\phi.
\]

Both say the same structural thing; the minus sign is common in physics, where force is minus the gradient of potential energy.

### What this does and does not mean

A vector field does not need to begin life as a gradient. Wind velocity and force are naturally described as vector fields because they have a direction at every point. The question is whether a particular vector field can be obtained from one scalar function:

- Temperature \(T\) is a scalar field. Its gradient \(\nabla T\), which points toward the fastest temperature increase, is a conservative vector field.
- A wind field is usually not conservative; it may circulate around a region and need not come from one scalar potential.
- A force field may or may not be conservative. Gravity is a standard conservative example; its force can be obtained from gravitational potential energy.

So “conservative” is a special property of a vector field, not another name for every vector field.

To show that a field is conservative, the cleanest route is often to find the potential directly. If you can differentiate one scalar function and recover the field, you have proved the claim.

## 3. Why \(\ln r\) appears

Let

> [!IMPORTANT]
> **Exam formula — radial distance**

\[
r=\sqrt{x^2+y^2+z^2}.
\]

### What “radial” means

A **radial vector** points directly away from or directly toward the origin. The position vector \(\vec r=x\hat i+y\hat j+z\hat k\) points from the origin to the current point, so it is radial. Its unit-length direction is

\[
\hat r=\frac{\vec r}{r}.
\]

A **radial field** has the form \(g(r)\hat r\): its direction is always away from or toward the origin, and its size depends only on distance \(r\), not on direction. In this question,

\[
\frac{\vec r}{r^2}=\frac1r\hat r.
\]

So \(\vec E\) points outward from the origin and has magnitude \(1/r\). It is undefined at the origin.

First find the gradient of \(r\):

To take a partial derivative with respect to \(x\), treat \(y\) and \(z\) as constants. Put \(u=x^2+y^2+z^2\). We use the chain rule

\[
\frac{d}{dx}(u^n)=nu^{n-1}\frac{du}{dx}.
\]

\[
\begin{aligned}
\frac{\partial r}{\partial x}
&=\frac{\partial}{\partial x}(x^2+y^2+z^2)^{1/2}
&&\text{[Chain rule: \(d(u^n)/dx=nu^{n-1}u'\)]}\\
&=\frac12(x^2+y^2+z^2)^{-1/2}(2x)
&&\text{[Power rule: \(d(x^2)/dx=2x\)]}\\
&=\frac{x}{\sqrt{x^2+y^2+z^2}}=\frac{x}{r}.
\end{aligned}
\]

Exactly the same calculation, while holding the other two variables constant, gives \(\partial r/\partial y=y/r\) and \(\partial r/\partial z=z/r\). Put these three partial derivatives together to form the gradient:

\[
\nabla r=\left\langle\frac{x}{r},\frac{y}{r},\frac{z}{r}\right\rangle=\frac{\vec r}{r}.
\]

Now use the chain rule on \(\ln r\):

> [!IMPORTANT]
> **Exam formula — radial field potential identity**

\[
\begin{aligned}
\nabla(\ln r)
&=\frac{d}{dr}(\ln r)\,\nabla r
&&\text{[Chain rule: \(\nabla[f(r)]=f'(r)\nabla r\)]}\\
&=\frac1r\left\langle\frac{x}{r},\frac{y}{r},\frac{z}{r}\right\rangle
&&\text{[Log rule: \(d(\ln r)/dr=1/r\)]}\\
&=\left\langle\frac{x}{r^2},\frac{y}{r^2},\frac{z}{r^2}\right\rangle
&=\frac{\vec r}{r^2}.
\end{aligned}
\]

Therefore \(\vec r/r^2\) is conservative everywhere except the origin, where \(r=0\) and the field is undefined.

Yes: proving \(\vec E=\nabla(\ln r)\) proves that \(\vec E\) is conservative for \(r>0\). The rest of the question uses a different sign convention: it wants a scalar potential \(\phi\) for which \(\vec E=-\nabla\phi\).

### Example

If \(\vec F=\vec r/r^2\) and the question asks for \(\vec F=-\nabla\phi\), then

\[
-\nabla\phi=\nabla(\ln r),
\]

so \(\phi=-\ln r+C\). Here the symbol is \(\phi\), pronounced “fai” (not \(\sigma\), sigma). If \(\phi=0\) at \(r=a\), then \(C=\ln a\), hence \(\phi=\ln(a/r)\). Notice that \(\ln(r/a)\) has the opposite sign and would give \(\nabla\phi=\vec E\), not \(-\nabla\phi=\vec E\).

> [!IMPORTANT]
> **Exam formula — when \(\vec F=\vec r/r^2=-\nabla\phi\) and \(\phi(a)=0\)**
>
> \(\displaystyle \phi=\ln\left(\frac{a}{r}\right),\quad r>0.\)

## 4. A practical potential-finding method

Suppose the question gives

\[
\vec F=P(x,y,z)\hat i+Q(x,y,z)\hat j+R(x,y,z)\hat k
\]

and asks for \(f\) such that \(\vec F=\nabla f\). We need one scalar function \(f(x,y,z)\) whose three partial derivatives match the three components:

> [!IMPORTANT]
> **Exam formula — recovering a potential**
>
> \(\displaystyle \frac{\partial f}{\partial x}=P,\qquad \frac{\partial f}{\partial y}=Q,\qquad \frac{\partial f}{\partial z}=R.\)

Use this workflow:

1. Integrate \(P\) with respect to \(x\).
2. Add an unknown function of the variables treated as constants, namely \(g(y,z)\). It is necessary because differentiating any function of \(y,z\) with respect to \(x\) gives zero.
3. Differentiate the result with respect to \(y\), then match it with \(Q\). This determines part or all of \(g(y,z)\).
4. Differentiate the result with respect to \(z\), then match it with \(R\). This determines what remains of \(g\).

### Worked example

Find a potential for

\[
\vec F=2xy\hat i+x^2\hat j+0\hat k.
\]

We first use \(\partial f/\partial x=2xy\). While integrating with respect to \(x\), treat \(y\) as a constant. The power rule is

\[
\int x^n\,dx=\frac{x^{n+1}}{n+1}+C\qquad(n\ne-1).
\]

\[
f=\int2xy\,dx=x^2y+g(y,z)
\qquad\text{[Power rule: \(\int x\,dx=x^2/2\)]}.
\]

Why is there a \(g_y\) term next? \(g(y,z)\) is not a number; it is an unknown function that may depend on \(y\) and \(z\). When taking \(\partial/\partial y\), \(z\) is held fixed but \(y\) is allowed to change. For example, if \(g(y,z)=y^3+5z\), then \(g_y=3y^2\). We must therefore keep \(g_y\) until matching the field tells us what it is.

Now match the \(\hat j\)-component. Differentiate the two terms separately with respect to \(y\):

\[
\frac{\partial f}{\partial y}
=\frac{\partial}{\partial y}[x^2y+g(y,z)]
=x^2+\frac{\partial g}{\partial y}
\qquad\text{[Sum rule: \(\partial(u+v)/\partial y=u_y+v_y\)]}
=Q=x^2.
\]

Therefore \(\partial g/\partial y=0\), so \(g\) cannot depend on \(y\): write \(g(y,z)=h(z)\). Next match the \(\hat k\)-component:

\[
\frac{\partial f}{\partial z}=h'(z)=R=0.
\]

Thus \(h(z)=C\), a constant, and

\[
\boxed{f=x^2y+C.}
\]

This method reappears throughout vector calculus.

## 5. Self-check

After finding a potential, do not trust it only because the algebra looked right. Check it in this order:

1. **Differentiate it.** Find \(\nabla f\) (or \(-\nabla\phi\), if the question uses that convention) and compare every component with the original field.
2. **Check the sign convention.** \(\vec F=\nabla f\) and \(\vec F=-\nabla\phi\) use opposite signs. A correct potential with the wrong convention produces the negative of the required field.
3. **Check the domain.** A field involving \(1/r\), \(1/r^2\), or \(\ln r\) is undefined at the origin, so state \(r>0\).
4. **Keep the arbitrary constant.** \(f+C\) has the same gradient as \(f\), because \(\nabla C=\vec0\). Use a given condition, such as \(\phi(a)=0\), to determine \(C\).

For the example above,

\[
\nabla(x^2y)=2xy\hat i+x^2\hat j+0\hat k,
\]

which exactly reproduces \(\vec F\). That is the strongest final check.
