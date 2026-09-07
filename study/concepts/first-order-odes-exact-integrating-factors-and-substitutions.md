# First-order ODEs: exact equations, integrating factors, and substitutions

Read [Differential equations: the ground floor](differential-equations-foundations.md) first. This note is the method map for the first-order equations in Q6 and Q7.

## 1. First identify the form

When an equation is written

\[
M(x,y)\,dx+N(x,y)\,dy=0,
\]

do not divide immediately. First ask whether the left side is the total differential of one hidden function \(\Phi(x,y)\). If it is, the equation is **exact**.

Imagine a height map. The total differential tells the tiny change in height after a tiny horizontal move \(dx\) and vertical move \(dy\). An exact equation says the combined change comes from one actual landscape \(\Phi\), so its solution is simply “stay on one contour”: \(\Phi=C\).

> [!IMPORTANT]
> **Exam test — exact differential equation**
>
> \[
> M(x,y)\,dx+N(x,y)\,dy=0
> \text{ is exact if }\frac{\partial M}{\partial y}=\frac{\partial N}{\partial x}.
> \]

The partial derivative \(\partial M/\partial y\) differentiates with respect to \(y\) while holding \(x\) fixed; \(\partial N/\partial x\) does the reverse.

### Solving an exact equation

1. Verify \(M_y=N_x\).
2. Integrate \(M\) with respect to \(x\): \(\Phi=\int M\,dx+g(y)\). The extra \(g(y)\) is needed because differentiating it with respect to \(x\) gives zero.
3. Differentiate \(\Phi\) with respect to \(y\), compare with \(N\), and find \(g'(y)\).
4. Integrate \(g'(y)\), then write \(\Phi=C\).

## 2. Integrating factor: making a non-exact form exact

An **integrating factor** is a nonzero multiplier \(\mu\) that changes a non-exact equation into an exact one. It is not a random extra symbol: it is chosen so the two mixed partial derivatives agree after multiplication.

For Q7(c), a quick test gives an integrating factor that depends only on \(y\):

> [!IMPORTANT]
> **Exam formula — integrating factor depending on \(y\)**
>
> If
> \[
> \frac{N_x-M_y}{M}=f(y),
> \]
> then
> \[
> \mu(y)=e^{\int f(y)\,dy}.
> \]

After multiplying both \(M\) and \(N\) by \(\mu(y)\), restart the exact-equation method from the beginning.

## 3. A nonlinear equation can become linear after the right substitution

Do not choose substitutions by guessing. Look for a repeated package. In Q7(b), the packages \(\sin 2y\) and \(\cos^2y\) point to \(u=\tan y\), because

> [!IMPORTANT]
> **Exam identities — the \(u=\tan y\) substitution**
>
> \[
> \sin 2y=2\sin y\cos y,
> \qquad
> \tan y=\frac{\sin y}{\cos y},
> \qquad
> \frac{d}{dx}(\tan y)=\sec^2y\frac{dy}{dx}.
> \]

Dividing by \(\cos^2y\) turns the equation into one involving \(d(\tan y)/dx\), which is a linear ODE in \(u\).

## 4. Solving a first-order linear ODE

For \(u'+P(x)u=Q(x)\), an **integrating factor** is a multiplier that turns the left side into one product derivative.

> [!IMPORTANT]
> **Exam formula — linear integrating factor**
>
> \[
> \operatorname{IF}=e^{\int P(x)\,dx},
> \qquad
> \frac{d}{dx}(\operatorname{IF}\cdot u)=\operatorname{IF}\cdot Q(x).
> \]

This works by the product rule: \(d(Iu)/dx=Iu'+I'u\), and \(I'=PI\). Integrate both sides and then divide by the integrating factor.
