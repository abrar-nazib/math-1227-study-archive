# Scalar Fields, Gradients, and Potential Functions

## 1. Scalar field versus vector field

A **scalar field** assigns one number to each point, such as temperature \(T(x,y,z)\). A **vector field** assigns a vector to each point, such as a force field

\[
\vec F(x,y,z)=P\hat i+Q\hat j+R\hat k.
\]

The gradient operator converts a scalar field into a vector field:

\[
\nabla\phi=\frac{\partial\phi}{\partial x}\hat i+
\frac{\partial\phi}{\partial y}\hat j+
\frac{\partial\phi}{\partial z}\hat k.
\]

Geometrically, \(\nabla\phi\) points in the direction where \(\phi\) increases most rapidly.

## 2. Conservative fields and potentials

A vector field is **conservative** when it comes from a scalar potential. Depending on the convention, one writes either

\[
\vec F=\nabla f \qquad\text{or}\qquad \vec F=-\nabla\phi.
\]

Both say the same structural thing; the minus sign is common in physics, where force is minus the gradient of potential energy.

To show that a field is conservative, the cleanest route is often to find the potential directly. If you can differentiate one scalar function and recover the field, you have proved the claim.

## 3. Why \(\ln r\) appears

Let

\[
r=\sqrt{x^2+y^2+z^2}.
\]

First find the gradient of \(r\):

\[
\nabla r=\left\langle\frac{x}{r},\frac{y}{r},\frac{z}{r}\right\rangle=\frac{\vec r}{r}.
\]

Now use the chain rule on \(\ln r\):

> [!IMPORTANT]
> **Exam formula — radial field potential identity**

\[
\nabla(\ln r)=\frac1r\nabla r=\frac{\vec r}{r^2}.
\]

Therefore \(\vec r/r^2\) is conservative everywhere except the origin, where \(r=0\) and the field is undefined.

### Example

If \(\vec F=\vec r/r^2\) and the question asks for \(\vec F=-\nabla\phi\), then

\[
-\nabla\phi=\nabla(\ln r),
\]

so \(\phi=-\ln r+C\). If \(\phi=0\) at \(r=a\), then \(C=\ln a\), hence \(\phi=\ln(a/r)\).

> [!IMPORTANT]
> **Exam formula — when \(\vec F=\vec r/r^2=-\nabla\phi\) and \(\phi(a)=0\)**
>
> \(\displaystyle \phi=\ln\left(\frac{a}{r}\right),\quad r>0.\)

## 4. A practical potential-finding method

For \(\vec F=P\hat i+Q\hat j+R\hat k\):

1. Integrate \(P\) with respect to \(x\).
2. Add an unknown function of the remaining variables.
3. Differentiate the result with respect to \(y\) and match \(Q\).
4. Repeat with \(z\) and match \(R\).

This method reappears throughout vector calculus.

## 5. Self-check

Always state the domain for a field involving \(1/r\), \(1/r^2\), or \(\ln r\): the origin must be excluded.
