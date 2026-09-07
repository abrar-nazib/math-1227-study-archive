# Differential equations: the ground floor

This note prepares you for 2024 Q6–Q8. Do not start by trying to memorise names such as “homogeneous” or “linear.” First identify what is changing, what it changes with, and what the equation is asking us to reconstruct.

## 1. What a differential equation says

An ordinary algebraic equation such as \(y=3x+1\) describes a finished relationship. A **differential equation (DE)** describes a relationship involving a rate of change, such as \(dy/dx\). Its solution is a function whose changing behaviour obeys that relationship.

Imagine a car trip. Position tells where the car is; velocity tells how position is changing; acceleration tells how velocity is changing. A DE may tell you a rule for the velocity or acceleration and ask you to recover the position curve.

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

## 4. General and particular solutions

A **general solution** contains arbitrary constants, such as \(C\). Those constants represent the many possible curves allowed by a rate rule. An **initial condition** selects one curve by giving a value at a particular input, for example \(i(0)=0\). Substituting that condition determines the constant and gives a **particular solution**.

For a first-order ODE, expect one arbitrary constant in its general solution. For a third-order ODE, expect three constants in its complementary solution.

## 5. Linear versus nonlinear

A differential equation is **linear in the dependent variable** if \(y\) and its derivatives appear only to the first power, are not multiplied by each other, and have coefficients depending only on the independent variable.

For example, \(dy/dx+P(x)y=Q(x)\) is linear. In contrast, \(y^2\), \((dy/dx)^2\), \(y(dy/dx)\), and \(\sin y\) make an equation nonlinear.

> [!IMPORTANT]
> **Exam form — first-order linear ODE**
>
> \[
> \frac{dy}{dx}+P(x)y=Q(x).
> \]

## 6. Two different meanings of “homogeneous”

This word causes real confusion because it is used in two different contexts.

1. A **linear ODE** is homogeneous when its forcing term is zero: \(L[y]=0\). It describes the system’s own natural behaviour. If \(L[y]=g(x)\) with \(g(x)\ne0\), it is non-homogeneous (forced).
2. A first-order equation such as \(dy/dx=F(y/x)\) is called homogeneous when its right-hand side depends only on the ratio \(y/x\). That is a different classification and uses the substitution \(y=vx\).

Q8(a) is non-homogeneous in the first sense. Q6(c) and Q7(a,c) are written as differential forms and are tested for exactness instead.

## 7. A first-order method chooser

These names describe the *shape* of an ODE. They are not competing labels to memorise blindly; inspect the equation and choose the pattern that exposes an integral.

- **Separable:** it can be rearranged as \(f(y)\,dy=g(x)\,dx\). Integrate each side separately.
- **First-order homogeneous:** it has the form \(dy/dx=F(y/x)\). Use \(y=vx\), so \(dy/dx=v+x\,dv/dx\).
- **Exact:** it is \(Mdx+Ndy=0\) with \(M_y=N_x\). Find a potential \(\Phi\) and write \(\Phi=C\).
- **Reducible to exact:** it is not exact, but an integrating factor makes it exact.
- **Linear:** it can be arranged as \(y'+P(x)y=Q(x)\). Use an integrating factor \(e^{\int Pdx}\).
- **Bernoulli:** it has the form \(y'+P(x)y=Q(x)y^n\), with \(n\ne0,1\). Use \(v=y^{1-n}\) to turn it into a linear equation.

Q6(c) is exact. Q7(b) becomes linear after \(u=\tan y\). Q7(c) is reducible to exact by an integrating factor. Q8(b) is already linear.

## 8. Why DEs matter

Differential equations turn a local rule—“how fast something changes right now”—into a complete model over time or space. Common applications include projectile and planetary motion, electric current in circuits, heat flow, vibration, population growth, radioactive decay, chemical reactions, and geometrical curves. In Q8(b), the local voltage-current rule determines the current at every time \(t\).
