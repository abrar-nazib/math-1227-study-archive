# Differential equations: the ground floor

This note prepares you for 2024 Q6–Q8. Do not start by trying to memorise names such as “homogeneous” or “linear.” First identify what is changing, what it changes with, and what the equation is asking us to reconstruct.

## 1. What a differential equation says

An ordinary algebraic equation such as \(y=3x+1\) describes a finished relationship. A **differential equation (DE)** describes a relationship involving a rate of change, such as \(dy/dx\). Its solution is a function whose changing behaviour obeys that relationship.

Imagine a car trip. Position tells where the car is; velocity tells how position is changing; acceleration tells how velocity is changing. A DE may tell you a rule for the velocity or acceleration and ask you to recover the position curve.

### First tiny example: recovering a function from its rate

Suppose a moving object's velocity rule is

\[
\frac{dy}{dx}=2x.
\]

The equation does not tell us the position \(y\) directly. It tells us how position changes. To recover \(y\), integrate both sides:

\[
dy=2x\,dx,
\]

\[
y=\int2x\,dx=x^2+C.
\]

[Power rule: \(\int x^n dx=x^{n+1}/(n+1)+C\).] The constant \(C\) is needed because every curve \(x^2+C\) has the same derivative \(2x\). A DE usually describes a family of possible curves until extra information selects one.

> [!IMPORTANT]
> **Exam definition — differential equation**
>
> A differential equation is an equation involving an unknown function and one or more of its derivatives.

## 2. ODE versus PDE

In an **ordinary differential equation (ODE)**, the unknown depends on one independent variable, so derivatives are ordinary derivatives. For example, \(y=y(x)\) and \(dy/dx\) is an ODE setting.

In a **partial differential equation (PDE)**, the unknown depends on two or more independent variables. For example, temperature \(T=T(x,t)\) can vary with position \(x\) and time \(t\); \(\partial T/\partial t\) and \(\partial T/\partial x\) are partial derivatives.

> [!IMPORTANT]
> **Exam distinction**
>
> \[
> \text{ODE: one independent variable; ordinary derivatives.}
> \]
>
> \[
> \text{PDE: two or more independent variables; partial derivatives.}
> \]

Q6–Q8 use **ODEs**, not PDEs.

### Compare two actual equations

\[
\frac{dy}{dx}+3y=x
\]

is an ODE: \(y\) depends only on \(x\), and there is one ordinary derivative.

\[
\frac{\partial T}{\partial t}=k\frac{\partial^2T}{\partial x^2}
\]

is a PDE: temperature \(T\) depends on both position \(x\) and time \(t\). The equation compares changes in two independent directions, so partial derivatives are required.

## 3. The basic vocabulary

- The **independent variable** is the input you choose, commonly \(x\) or time \(t\).
- The **dependent variable** is the output that responds, commonly \(y(x)\) or current \(i(t)\).
- A **derivative** measures an instantaneous rate of change. \(y'\), \(dy/dx\), and \(Dy\) all mean the first derivative when the independent variable is \(x\).
- The **order** is the order of the highest derivative present. \(y''+y=0\) is second order; \(y'''+y=0\) is third order.
- The **degree** is the power of the highest-order derivative after the equation has been made polynomial in derivatives. Q6–Q8 use degree-one equations.

> [!IMPORTANT]
> **Exam definition — order**
>
> The order of a differential equation is the order of its highest derivative.

### Order and degree examples

\[
\frac{d^2y}{dx^2}+5\frac{dy}{dx}-y=0
\]

has highest derivative \(d^2y/dx^2\), so it is **second order**. That derivative has power \(1\), so its degree is \(1\).

\[
\left(\frac{d^3y}{dx^3}\right)^2+\frac{dy}{dx}=x
\]

has highest derivative \(d^3y/dx^3\), so it is **third order**. That highest derivative is squared, so its degree is \(2\).

## 4. General and particular solutions

A **general solution** contains arbitrary constants, such as \(C\). Those constants represent the many possible curves allowed by a rate rule. An **initial condition** selects one curve by giving a value at a particular input, for example \(i(0)=0\). Substituting that condition determines the constant and gives a **particular solution**.

For a first-order ODE, expect one arbitrary constant in its general solution. For a third-order ODE, expect three constants in its complementary solution.

### One rule, many curves; one condition, one curve

Return to

\[
\frac{dy}{dx}=2x.
\]

Its general solution is

\[
y=x^2+C.
\]

If the initial condition is \(y(0)=5\), substitute \(x=0\) and \(y=5\):

\[
5=0^2+C,
\]

\[
C=5.
\]

Thus the particular solution is

\[
y=x^2+5.
\]

Checking it: \(d(x^2+5)/dx=2x\), and at \(x=0\) its value is \(5\).

## 5. Linear versus nonlinear

A differential equation is **linear in the dependent variable** if \(y\) and its derivatives appear only to the first power, are not multiplied by each other, and have coefficients depending only on the independent variable.

For example, \(dy/dx+P(x)y=Q(x)\) is linear. In contrast, \(y^2\), \((dy/dx)^2\), \(y(dy/dx)\), and \(\sin y\) make an equation nonlinear.

> [!IMPORTANT]
> **Exam form — first-order linear ODE**
>
> \[
> \frac{dy}{dx}+P(x)y=Q(x).
> \]

### Classification examples

\[
\frac{dy}{dx}+x^2y=\sin x
\]

is linear. The coefficient \(x^2\) depends only on \(x\), and both \(y\) and \(dy/dx\) occur to the first power.

\[
\frac{dy}{dx}+x^2y^2=\sin x
\]

is nonlinear because \(y^2\) occurs.

\[
y\frac{dy}{dx}+x=0
\]

is nonlinear because the dependent variable \(y\) multiplies its derivative.

## 6. Two different meanings of “homogeneous”

This word causes real confusion because it is used in two different contexts.

1. A **linear ODE** is homogeneous when its forcing term is zero: \(L[y]=0\). It describes the system’s own natural behaviour. If \(L[y]=g(x)\) with \(g(x)\ne0\), it is non-homogeneous (forced).
2. A first-order equation such as \(dy/dx=F(y/x)\) is called homogeneous when its right-hand side depends only on the ratio \(y/x\). That is a different classification and uses the substitution \(y=vx\).

Q8(a) is non-homogeneous in the first sense. Q6(c) and Q7(a,c) are written as differential forms and are tested for exactness instead.

### Put the two meanings side by side

\[
y''+4y=0
\]

is a **homogeneous linear** equation because its right side is zero. In a physical vibration model, it represents the system moving with no continuing external push.

\[
y''+4y=\cos x
\]

is **non-homogeneous linear** because \(\cos x\) is an external forcing term.

In contrast,

\[
\frac{dy}{dx}=1+\frac{y}{x}
\]

is **homogeneous in the first-order ratio sense**, because its right side is a function of \(y/x\) only. It has nothing to do with whether the right side is zero.

## 7. A first-order method chooser

These names describe the *shape* of an ODE. They are not competing labels to memorise blindly; inspect the equation and choose the pattern that exposes an integral.

- **Separable:** it can be rearranged as \(f(y)\,dy=g(x)\,dx\). Integrate each side separately.
- **First-order homogeneous:** it has the form \(dy/dx=F(y/x)\). Use \(y=vx\), so \(dy/dx=v+x\,dv/dx\).
- **Exact:** it is \(Mdx+Ndy=0\) with \(M_y=N_x\). Find a potential \(\Phi\) and write \(\Phi=C\).
- **Reducible to exact:** it is not exact, but an integrating factor makes it exact.
- **Linear:** it can be arranged as \(y'+P(x)y=Q(x)\). Use an integrating factor \(e^{\int Pdx}\).
- **Bernoulli:** it has the form \(y'+P(x)y=Q(x)y^n\), with \(n\ne0,1\). Use \(v=y^{1-n}\) to turn it into a linear equation.

Q6(c) is exact. Q7(b) becomes linear after \(u=\tan y\). Q7(c) is reducible to exact by an integrating factor. Q8(b) is already linear.

### Recognition examples before you solve

**Separable:**

\[
\frac{dy}{dx}=xy.
\]

Move the \(y\) factor with \(dy\):

\[
\frac{1}{y}\,dy=x\,dx.
\]

That is separable because the left contains only \(y\), and the right contains only \(x\).

**Exact:**

\[
2xy\,dx+x^2\,dy=0.
\]

Here \(M=2xy\) and \(N=x^2\). The test gives

\[
M_y=2x,
\qquad N_x=2x.
\]

They match, so it is exact. In fact the left side is \(d(x^2y)\), so the solution is \(x^2y=C\).

**Linear:**

\[
\frac{dy}{dx}+2y=x.
\]

It matches \(y'+P(x)y=Q(x)\) with \(P(x)=2\) and \(Q(x)=x\). This tells you to use the linear integrating-factor method.

**Bernoulli:**

\[
\frac{dy}{dx}+y=xy^2.
\]

It has the pattern \(y'+P(x)y=Q(x)y^n\), here \(P(x)=1\), \(Q(x)=x\), and \(n=2\). It is nonlinear in \(y\), but \(v=y^{1-2}=y^{-1}\) changes it into a linear equation for \(v\).

**Reducible to exact:** Q7(c) is the exam example. Its two partial derivatives initially do not match, but a multiplier depending only on \(y\) makes them match. See [the full worked calculation](../2024/q7-study-guide.md#q7c-integrating-factor-depending-on-y).

## 8. Why DEs matter

Differential equations turn a local rule—“how fast something changes right now”—into a complete model over time or space. Common applications include projectile and planetary motion, electric current in circuits, heat flow, vibration, population growth, radioactive decay, chemical reactions, and geometrical curves. In Q8(b), the local voltage-current rule determines the current at every time \(t\).
