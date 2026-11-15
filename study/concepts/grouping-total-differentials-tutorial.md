# Grouping method: from tiny changes to exact equations

This note teaches the grouping method slowly, from the beginning. Its purpose is to help you **recognize and check** the pieces of a total differential—not to make you guess an answer. The existing [exact-equation method note](first-order-odes-exact-integrating-factors-and-substitutions.md#1-first-identify-the-form) explains the broader test and systematic potential method. The [calculus reference](differentiation-and-integration-reference.md) is there if a differentiation rule needs refreshing.

## 1. What is the problem we are trying to solve?

Imagine walking on a landscape. Every point has a height \(F(x,y)\). A tiny step can change your height because you moved in the \(x\)-direction, because you moved in the \(y\)-direction, or both. A differential records the contributions to that change.

An exact equation can be written as

\[
dF=0.
\]

Along a solution curve, the total change in \(F\) is zero. So you stay on a contour of constant height:

\[
F(x,y)=C.
\]

Here \(C\) is an arbitrary constant: different choices can describe different contours. The **grouping method** starts with the differential pieces and works backwards to identify \(F\).

The essential idea is a puzzle: differentiation takes one expression apart into pieces; grouping tries to put those exact pieces back together. We check a proposed group by differentiating it forward.

## 2. What do dx, dy and dF mean?

For a differentiable function of one variable, \(dF=F'(x)\,dx\). You can think of \(dx\) as a small input change, and \(dF\) as the corresponding **linear part** of the change in \(F\). For a finite change it is an approximation; the differential itself is the exact linear expression defined by the derivative.

For a differentiable function of two variables,

\[
dF=\frac{\partial F}{\partial x}\,dx+
\frac{\partial F}{\partial y}\,dy.
\]

The first term is the contribution associated with the \(x\)-direction; the second is associated with the \(y\)-direction. \(F_x\) means differentiate in \(x\) holding \(y\) fixed, while \(F_y\) means differentiate in \(y\) holding \(x\) fixed.

For example, take \(F=x+y\). [Rules: \(\partial x/\partial x=1\), \(\partial y/\partial x=0\), \(\partial x/\partial y=0\), and \(\partial y/\partial y=1\).] Then

\[
\begin{aligned}
F_x&=1+0=1,\\
F_y&=0+1=1,\\
dF&=1\,dx+1\,dy\\
&=dx+dy.
\end{aligned}
\]

So if an equation contains \(dx+dy=0\), we can recognize it as \(d(x+y)=0\), giving \(x+y=C\). For a concrete picture, a step to the right can be balanced by a step down, keeping their sum unchanged. **Neither differential has to be zero individually.**

Along a differentiable graph \(y=y(x)\), the same equation can be written \(F_x+F_y\,dy/dx=0\), because [chain rule: \(dF(x,y(x))/dx=F_x+F_y\,dy/dx\)]. This is why \(dF=0\) means that \(F\) stays constant as we follow the solution.

## 3. First puzzle pieces: one variable at a time

For a differentiable one-variable function, the differential form of the power rule is

\[
d(x^n)=nx^{n-1}dx,\qquad d(y^n)=ny^{n-1}dy.
\]

Read these both ways: the left side **produces** the right side; if you see the right side, you can **recognize** the left side.

### Example 1: two single pieces

Solve

\[
2x\,dx+3y^2\,dy=0.
\]

The actual rules are \(d(x^2)=2x\,dx\) and \(d(y^3)=3y^2\,dy\). Replace each piece:

\[
\begin{aligned}
2x\,dx+3y^2\,dy&=0,\\
d(x^2)+d(y^3)&=0,\\
d(x^2+y^3)&=0,\\
\boxed{x^2+y^3&=C.}
\end{aligned}
\]

In the third line we used linearity, \(d(A+B)=dA+dB\); in the fourth, \(\int dG=G+C\), or equivalently a function with zero derivative along a connected curve is constant there.

**Check:** [Power rule: \(d(x^n)=nx^{n-1}dx\), \(d(y^n)=ny^{n-1}dy\).]

\[
\begin{aligned}
d(x^2+y^3)
&=d(x^2)+d(y^3)\\
&=2x\,dx+3y^2\,dy.
\end{aligned}
\]

That reproduces the original left side. Notice how the coefficient and power both need to match.

### Try a tiny check

For \(5x^4dx\), the matching piece is \(d(x^5)\), because \(d(x^5)=5x^4dx\). For \(x\,dx\), the matching piece is \(d(x^2/2)\), because \(d(x^2/2)=\tfrac12(2x\,dx)=x\,dx\). The factor of one half is necessary.

## 4. The crucial new piece: a product changes in two ways

Think of a rectangle with sides \(x\) and \(y\). Its area is \(xy\). A small change of width contributes \(y\,dx\) to the linear change in area; a small change of height contributes \(x\,dy\). Together:

> [!IMPORTANT]
> **Exam formula — product rule for differentials**
>
> \[
> d(uv)=u\,dv+v\,du.
> \]
>
> In particular, \(d(xy)=x\,dy+y\,dx\).

This is the exact differential formula, not the exact finite area difference: the finite difference also has a \(\Delta x\Delta y\) term. The differential records the linear part.

### Example 2: recognize a pair

Consider

\[
y\,dx+x\,dy=0.
\]

The first term alone is **not** the whole differential of \(xy\). Check both halves:

\[
\begin{aligned}
d(xy)&=x\,dy+y\,dx\\
&=y\,dx+x\,dy.
\end{aligned}
\]

The order of addition does not matter. Therefore

\[
\begin{aligned}
y\,dx+x\,dy&=0,\\
d(xy)&=0,\\
\boxed{xy&=C.}
\end{aligned}
\]

**Check:** with \(y\) held fixed, \(\partial(xy)/\partial x=y\); with \(x\) held fixed, \(\partial(xy)/\partial y=x\). Thus \(d(xy)=y\,dx+x\,dy\), exactly as required.

## 5. How do I discover the product instead of guessing?

Here is a repeatable way to test a possible group. Suppose the terms are

\[
2xy\,dx+x^2\,dy.
\]

1. Look at the \(dy\)-coefficient: it is \(x^2\). Ask what expression has \(y\)-partial derivative \(x^2\). One candidate is \(x^2y\).
2. Check the **other** piece: does its \(x\)-partial derivative give \(2xy\)? Yes.
3. Combine the two pieces only after both match.

Show the check in full. [Product rule: \(d(uv)=u\,dv+v\,du\); power rule: \(d(x^2)=2x\,dx\).] Let \(u=x^2\), \(v=y\):

\[
\begin{aligned}
d(x^2y)
&=x^2\,d(y)+y\,d(x^2)\\
&=x^2\,dy+y(2x\,dx)\\
&=x^2\,dy+2xy\,dx\\
&=2xy\,dx+x^2\,dy.
\end{aligned}
\]

Equivalently, from the \(dx\)-term you could integrate \(2xy\) in \(x\), holding \(y\) fixed. [Rule: \(\int x\,dx=x^2/2+C\).] This gives \(x^2y\), and the same second check follows.

The matching pieces need not be adjacent in the question. You may reorder terms using ordinary addition, but use each term exactly once.

## 6. A full example with a product and two single pieces

Solve

\[
(2xy+2x)dx+(x^2+3y^2)dy=0.
\]

**Map:** expand; find a product pair; recognize the single-variable pieces; combine; check. This is the same principle as the KH Problem 6 example, but with a different equation.

First expand:

\[
\begin{aligned}
(2xy+2x)dx+(x^2+3y^2)dy&=0,\\
2xy\,dx+2x\,dx+x^2\,dy+3y^2\,dy&=0.
\end{aligned}
\]

Rearrange terms so the matching product pieces sit together:

\[
\underbrace{(2xy\,dx+x^2\,dy)}_{d(x^2y)}
+\underbrace{2x\,dx}_{d(x^2)}
+\underbrace{3y^2\,dy}_{d(y^3)}=0.
\]

The first match was checked in section 5; the other two use \(d(x^2)=2x\,dx\) and \(d(y^3)=3y^2\,dy\). Replace, combine by \(d(A+B+C)=dA+dB+dC\), and integrate \(dG=0\):

\[
\begin{aligned}
d(x^2y)+d(x^2)+d(y^3)&=0,\\
d(x^2y+x^2+y^3)&=0,\\
\boxed{x^2y+x^2+y^3&=C.}
\end{aligned}
\]

**Check:** calculate both partial derivatives while holding the other variable fixed. [Power rule: \(d(u^n)/du=nu^{n-1}\).]

\[
\begin{aligned}
F_x&=2xy+2x+0=2xy+2x,\\
F_y&=x^2+0+3y^2=x^2+3y^2.
\end{aligned}
\]

They match the original \(dx\) and \(dy\) coefficients, respectively.

## 7. A harder product: an exponential or trig function

The same product rule works when the pieces are not powers. Consider

\[
e^y\,dx+xe^y\,dy=0.
\]

The \(dx\)-coefficient \(e^y\) suggests \(F=xe^y\), because holding \(y\) fixed gives \(F_x=e^y\). Check the \(dy\)-coefficient too. [Product rule: \(d(uv)=u\,dv+v\,du\); exponential rule: \(d(e^y)=e^y\,dy\).]

\[
\begin{aligned}
d(xe^y)
&=x\,d(e^y)+e^y\,d(x)\\
&=xe^y\,dy+e^y\,dx\\
&=e^y\,dx+xe^y\,dy.
\end{aligned}
\]

Both pieces match. Hence

\[
d(xe^y)=0,\qquad xe^y=C.
\]

For a trig example, the same process uses \(d(\cos y)=-\sin y\,dy\):

\[
\begin{aligned}
d(x^2\cos y)
&=x^2d(\cos y)+\cos y\,d(x^2)\\
&=x^2(-\sin y\,dy)+\cos y(2x\,dx)\\
&=2x\cos y\,dx-x^2\sin y\,dy.
\end{aligned}
\]

The minus sign is part of the group. If a question contains only one of these two terms, do not pretend the other is there.

## 8. A common trap: a promising pair that does not match

Suppose you see

\[
y\,dx+2x\,dy.
\]

It resembles \(d(xy)\), but the product rule gives

\[
d(xy)=y\,dx+x\,dy,
\]

and the second coefficient is \(x\), not \(2x\). So replacing the original pair with \(d(xy)\) would change the equation. You might consider another candidate, but the reliable check is always to calculate *both* partial derivatives.

More generally, the grouping shortcut is easiest when whole matching pieces can be recognized. It is not a promise that every expression can be split by inspection. If you cannot find a match, use the [systematic potential method](first-order-odes-exact-integrating-factors-and-substitutions.md#1-first-identify-the-form); if the equation is not exact, it may need an integrating factor first.

## 9. Your repeatable checklist

1. Expand brackets so every \(dx\) and \(dy\) term is visible.
2. Look for single-variable pieces such as \(2x\,dx=d(x^2)\).
3. For mixed pieces, use one coefficient to propose a product; differentiate the proposal in **both** directions.
4. Rearrange and group matching terms, using each term once. Keep every sign and constant.
5. Combine using \(d(A+B)=dA+dB\), then use \(dF=0\Rightarrow F=C\) along a connected solution curve.
6. Check \(F_x=M\) and \(F_y=N\) against the original equation. If a factor was used or a quantity divided out, check where it is zero or undefined separately.

## 10. Practise, then compare

Try grouping this equation yourself:

\[
(2xy+1)dx+(x^2+2y)dy=0.
\]

Hint: the mixed pair is the one checked in section 5. The remaining pieces are \(dx\) and \(2y\,dy\).

<details>
<summary>Show the solution and check</summary>

Using \(d(x^2y)=2xy\,dx+x^2\,dy\), \(d(x)=dx\), and \(d(y^2)=2y\,dy\):

\[
\begin{aligned}
2xy\,dx+dx+x^2\,dy+2y\,dy&=0,\\
d(x^2y)+d(x)+d(y^2)&=0,\\
d(x^2y+x+y^2)&=0,\\
x^2y+x+y^2&=C.
\end{aligned}
\]

Check with \(F=x^2y+x+y^2\): \(F_x=2xy+1\), \(F_y=x^2+2y\), exactly the original coefficients.

</details>

Once these examples feel comfortable, return to the [KH Problem 6 grouping walkthrough](../class-note-explanations/kh/chapter-2-problem-6-exact-equation.md#5-the-grouping-method-on-pdf-page-6). It applies the same checks to the problem in your class notes.
