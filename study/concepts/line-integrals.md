# Line Integrals of Vector Fields

## 1. What \(\int_C\vec F\cdot d\vec r\) means

A line integral adds the component of a vector field tangent to a path. In mechanics, it is the work done by a force \(\vec F\) as an object travels along \(C\).

If the path is parameterized by

\[
\vec r(t)=\langle x(t),y(t),z(t)\rangle,\qquad a\le t\le b,
\]

then

\[
d\vec r=\vec r\,'(t)dt
\]

and

\[
\int_C\vec F\cdot d\vec r=
\int_a^b\vec F(\vec r(t))\cdot\vec r\,'(t)\,dt.
\]

## 2. The reliable workflow

1. Parameterize the path in the stated direction.
2. Find \(d\vec r\), or \(dx,dy,dz\).
3. Substitute the parameterization into the field.
4. Take the dot product.
5. Integrate using limits that match the direction.

For \(\vec F=P\hat i+Q\hat j+R\hat k\), an equivalent form is

\[
\int_C P\,dx+Q\,dy+R\,dz.
\]

## 3. A circle in the plane \(z=1\)

The circle \(x^2+y^2=1, z=1\) can be written as

\[
x=\cos\theta,\qquad y=\sin\theta,\qquad z=1.
\]

Then

\[
dx=-\sin\theta\,d\theta,\qquad dy=\cos\theta\,d\theta,\qquad dz=0.
\]

The endpoint \((0,1,1)\) corresponds to \(\theta=\pi/2\); \((1,0,1)\) corresponds to \(\theta=0\). Therefore the stated trip uses \(\theta:\pi/2\to0\). Reversing these limits reverses the sign of the line integral.

## 4. Small example

Let \(\vec F=y\hat i+x\hat j\), and follow the quarter circle from \((1,0)\) to \((0,1)\). With \(x=\cos\theta,y=\sin\theta\), \(0\le\theta\le\pi/2\),

\[
\vec F\cdot d\vec r=y\,dx+x\,dy
=\sin\theta(-\sin\theta)d\theta+\cos\theta(\cos\theta)d\theta.
\]

The integrand is \(\cos^2\theta-\sin^2\theta\). The key lesson is not the final number: the parameter bounds encode the travel direction.

## 5. Common mistakes

- Forgetting that \(dz=0\) when \(z\) is constant.
- Substituting into \(\vec F\) but not into \(dx,dy,dz\).
- Using counter-clockwise bounds when the endpoints specify clockwise travel.
