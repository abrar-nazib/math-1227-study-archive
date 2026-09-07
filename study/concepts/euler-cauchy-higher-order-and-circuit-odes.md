# Higher-order Euler–Cauchy equations and circuit ODEs

Read [Differential equations: the ground floor](differential-equations-foundations.md) first. This note supports Q8.

## 1. Higher-order linear equations: natural response plus forcing

A linear higher-order ODE can be written as \(L[y]=g(x)\). Its full solution is split into two jobs:

> [!IMPORTANT]
> **Exam structure — complete solution**
>
> \[
> y=\text{CF}+\text{PI}.
> \]
>
> CF (complementary function) solves \(L[y]=0\); PI (particular integral) is one solution of \(L[y]=g(x)\).

Picture a bell: CF is how it rings after being struck and then left alone; PI is the continuing behaviour caused by an external forcing input. Their sum solves the full equation.

## 2. Euler–Cauchy form

An **Euler–Cauchy** equation has derivative coefficients that use matching powers of \(x\), for example

\[
x^3y'''+a_1xy'+a_0y=g(x).
\]

Try \(y=x^m\). Each term becomes a constant multiple of \(x^m\), so the differential equation becomes an algebraic **auxiliary equation** for \(m\).

> [!IMPORTANT]
> **Exam rule — Euler trial function**
>
> \[
> y=x^m,\quad y'=mx^{m-1},\quad y'''=m(m-1)(m-2)x^{m-3}.
> \]

For roots \(m=\alpha\pm i\beta\), the real CF terms are

> [!IMPORTANT]
> **Exam formula — complex Euler roots**
>
> \[
> x^\alpha\bigl(C_1\cos(\beta\ln x)+C_2\sin(\beta\ln x)\bigr),\qquad x>0.
> \]

## 3. The \(\theta\) operator shortcut

> [!IMPORTANT]
> **Exam formula — \(\theta\) operator for Q8(a)**
>
> Define \(\theta=x\,d/dx\). On \(x^m\), it acts like multiplication by \(m\): \(\theta(x^m)=mx^m\). For Q8(a),
>
> \[
> x^3D^3=\theta(\theta-1)(\theta-2).
> \]

This explains why the auxiliary polynomial is \(F(m)=m(m-1)(m-2)+2m-2\). It also makes the particular integral manageable.

## 4. First-order RL circuit equation

> [!IMPORTANT]
> **Exam model — RL circuit equation**
>
> For an inductor \(L\), resistor \(R\), supplied voltage \(v(t)\), and current \(i(t)\),
>
> \[
> L\frac{di}{dt}+Ri=v(t).
> \]

This is just a first-order linear ODE. Divide by \(L\), use the linear integrating factor from [the first-order note](first-order-odes-exact-integrating-factors-and-substitutions.md#4-solving-a-first-order-linear-ode), and use the initial current to choose the one physical solution.
