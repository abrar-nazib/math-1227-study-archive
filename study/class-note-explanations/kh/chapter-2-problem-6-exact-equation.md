# KH Chapter 2, Problem 6: how the function F is formed

The problem on PDF page 5 asks us to solve

\[
(3x^2+4xy)\,dx+(2x^2+2y)\,dy=0.
\]

The confusing step is where the notes suddenly write a function \(F\). We are **reconstructing** that function from its partial derivatives. For the general idea of an exact equation, see [the exact-equation concept note](../../concepts/first-order-odes-exact-integrating-factors-and-substitutions.md); for the general reason an unknown function appears, see [the potential-function example](../../concepts/scalar-fields-gradient-and-potential.md).

## What are we looking for?

Think of \(F(x,y)\) as an unknown height map. We are told how its height changes in the \(x\) direction and in the \(y\) direction, and want to reconstruct a map matching both pieces of information.

For an exact equation, the total differential of a function \(F\) is

\[
dF=\frac{\partial F}{\partial x}\,dx+\frac{\partial F}{\partial y}\,dy.
\]

In the question, let

\[
M(x,y)=3x^2+4xy,\qquad N(x,y)=2x^2+2y.
\]

Matching the coefficients of \(dx\) and \(dy\) means we seek a function satisfying **both**

\[
\frac{\partial F}{\partial x}=3x^2+4xy,\qquad
\frac{\partial F}{\partial y}=2x^2+2y.
\]

If we find it, the given equation becomes \(dF=0\). Along a solution curve, the value of \(F\) stays constant, giving \(F(x,y)=C\).

## 1. Check that the equation is exact

Here \(M\) and \(N\) are polynomials, with continuous derivatives on the entire plane. For such functions on this domain, matching the mixed partials is sufficient for exactness.

Differentiate \(M\) with respect to \(y\), holding \(x\) constant. [Rules: \(\partial y/\partial y=1\), \(\partial c/\partial y=0\) for a quantity \(c\) fixed with respect to \(y\).]

\[
\begin{aligned}
\frac{\partial M}{\partial y}
&=\frac{\partial}{\partial y}(3x^2+4xy)\\
&=0+4x(1)\\
&=4x.
\end{aligned}
\]

Differentiate \(N\) with respect to \(x\), holding \(y\) constant. [Rules: \(\partial x^2/\partial x=2x\), \(\partial y/\partial x=0\).]

\[
\begin{aligned}
\frac{\partial N}{\partial x}
&=\frac{\partial}{\partial x}(2x^2+2y)\\
&=2(2x)+0\\
&=4x.
\end{aligned}
\]

The results match, so this equation is exact.

## 2. Build the first part of F by integrating M

We know \(F_x=3x^2+4xy\). To reverse differentiation with respect to \(x\), integrate with respect to \(x\), treating \(y\) as a constant. [Rules: \(\int x^n\,dx=x^{n+1}/(n+1)+C\) for \(n\ne-1\), and \(\int c f(x)\,dx=c\int f(x)\,dx\) when \(c\) is fixed with respect to \(x\).]

\[
\begin{aligned}
F(x,y)
&=\int(3x^2+4xy)\,dx\\
&=3\int x^2\,dx+4y\int x\,dx\\
&=3\left(\frac{x^3}{3}\right)+4y\left(\frac{x^2}{2}\right)+f(y)\\
&=x^3+2x^2y+f(y).
\end{aligned}
\]

That is the line the notes write down without showing the calculation. The last term \(f(y)\) is an **unknown function of \(y\)**, not yet a known number. Why? Differentiating with respect to \(x\) makes *any* function depending only on \(y\) disappear. For instance, all three of these give the same \(F_x\):

\[
x^3+2x^2y,\quad x^3+2x^2y+y^2,\quad x^3+2x^2y+\sin y.
\]

So the \(x\)-derivative alone cannot tell us what the \(y\)-only part is. We keep \(f(y)\) as a placeholder until the other partial derivative supplies that information.

## 3. Use N to find the missing function

Now differentiate our candidate \(F=x^3+2x^2y+f(y)\) with respect to \(y\), holding \(x\) constant. [Rules: \(\partial c/\partial y=0\) for \(c\) fixed with respect to \(y\), \(\partial y/\partial y=1\), and \(d[f(y)]/dy=f'(y)\).]

\[
\begin{aligned}
\frac{\partial F}{\partial y}
&=\frac{\partial}{\partial y}\left(x^3+2x^2y+f(y)\right)\\
&=0+2x^2(1)+f'(y)\\
&=2x^2+f'(y).
\end{aligned}
\]

The derivative of \(f(y)\) is not zero here: we are now differentiating with respect to **y**, the variable on which it depends. We also need \(F_y=N=2x^2+2y\), so match them:

\[
\begin{aligned}
2x^2+f'(y)&=2x^2+2y,\\
f'(y)&=2y.
\end{aligned}
\]

Integrate with respect to \(y\). [Power rule: \(\int y^n\,dy=y^{n+1}/(n+1)+C\), for \(n\ne-1\).]

\[
\begin{aligned}
f(y)&=\int2y\,dy\\
&=2\left(\frac{y^2}{2}\right)+C_0\\
&=y^2+C_0.
\end{aligned}
\]

Substitute back:

\[
F=x^3+2x^2y+y^2+C_0.
\]

Since the solution is \(F=C_1\), the ordinary additive constant \(C_0\) can be moved to the other side and absorbed into a new constant \(C=C_1-C_0\). Thus

\[
\boxed{x^3+2x^2y+y^2=C.}
\]

## 4. Check both parts

Choose \(F=x^3+2x^2y+y^2\). Using \(d(x^n)/dx=nx^{n-1}\) and treating the other variable as constant for each partial derivative:

\[
\begin{aligned}
F_x&=3x^2+2y(2x)+0=3x^2+4xy=M,\\
F_y&=0+2x^2+2y=N.
\end{aligned}
\]

Both match the original coefficients. Therefore \(dF=M\,dx+N\,dy\), and setting \(F=C\) gives the required implicit solution.
