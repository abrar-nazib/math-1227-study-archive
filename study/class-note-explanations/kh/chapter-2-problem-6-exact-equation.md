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

## 5. The grouping method on PDF page 6

Page 6 first presents an “another method” using the \(x\)-free part of \(N\), and then a separate **method of grouping**. The grouping method is like putting puzzle pieces together: look for terms that together form the total differential of one familiar expression. Then combine those smaller differentials into one.

### First, an easy example

Suppose we see

\[
y\,dx+x\,dy=0.
\]

The two pieces may look unrelated until we recall the product rule. For functions \(u\) and \(v\),

\[
d(uv)=u\,dv+v\,du.
\]

Choose \(u=x\) and \(v=y\). Then \(du=dx\) and \(dv=dy\), so

\[
\begin{aligned}
d(xy)&=x\,dy+y\,dx\\
&=y\,dx+x\,dy.
\end{aligned}
\]

Therefore the original two pieces are exactly one total differential:

\[
\begin{aligned}
y\,dx+x\,dy&=0,\\
d(xy)&=0,\\
xy&=C.
\end{aligned}
\]

The last step uses \(\int dG=G+C\): if the total change of \(G\) along a solution curve is zero, \(G\) remains constant there. It does **not** say that \(dx\) and \(dy\) must individually be zero; their contributions can cancel along the curve.

### Now group the terms in Problem 6

First expand the brackets in the given equation:

\[
\begin{aligned}
(3x^2+4xy)\,dx+(2x^2+2y)\,dy&=0,\\
3x^2\,dx+4xy\,dx+2x^2\,dy+2y\,dy&=0.
\end{aligned}
\]

There are four terms. We will recognize the first and last separately and the two middle terms **as a pair**.

**First term.** [Power rule for differentials: \(d(x^n)=nx^{n-1}dx\).] With \(n=3\),

\[
d(x^3)=3x^2\,dx.
\]

**Last term.** The same power rule, with \(y\) as the variable and \(n=2\), gives

\[
d(y^2)=2y\,dy.
\]

**The middle pair.** We want to recognize

\[
4xy\,dx+2x^2\,dy.
\]

The \(dy\) term suggests the product \(2x^2y\): differentiating that product with respect to \(y\), while holding \(x\) fixed, gives \(2x^2\). Let's check **both** pieces using \(d(uv)=u\,dv+v\,du\), and the power rule \(d(x^2)=2x\,dx\):

\[
\begin{aligned}
d(2x^2y)
&=2\,d(x^2y)\\
&=2\left(x^2\,dy+y\,d(x^2)\right)\\
&=2\left(x^2\,dy+y(2x\,dx)\right)\\
&=2x^2\,dy+4xy\,dx\\
&=4xy\,dx+2x^2\,dy.
\end{aligned}
\]

Both required terms are present, with the correct coefficients. This check is important: recognizing only one half of a product differential is not enough.

Now replace each group in the expanded original equation:

\[
\begin{aligned}
3x^2\,dx+\bigl(4xy\,dx+2x^2\,dy\bigr)+2y\,dy&=0,\\
d(x^3)+d(2x^2y)+d(y^2)&=0.
\end{aligned}
\]

By linearity, \(d(A+B+C)=dA+dB+dC\). Apply it in reverse:

\[
\begin{aligned}
d\left(x^3+2x^2y+y^2\right)&=0,\\
\boxed{x^3+2x^2y+y^2&=C.}
\end{aligned}
\]

Again, \(dG=0\) along a solution means \(G\) is constant along that curve. This is the same implicit solution obtained by constructing \(F\) above.

### How does this relate to the other shortcut?

The preceding “another method” integrates \(M\) with respect to \(x\), giving \(x^3+2x^2y\), then adds the missing \(y\)-only contribution \(y^2\). Here that shortcut works because the \(2x^2\) part of \(N\) is already accounted for when differentiating \(2x^2y\) with respect to \(y\). More generally, don't blindly add all of \(N\): compare it with the \(y\)-derivative of what you already found, or you can count a term twice. The main method in sections 2–3 performs that comparison explicitly.

Grouping can be quick when the pieces are recognizable. If a match isn't obvious, the systematic \(F_x=M\), then \(F_y=N\), method is a reliable alternative.
