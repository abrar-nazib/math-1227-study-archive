# Math 1227 — 2024 Q8 study guide

Read [Higher-order Euler–Cauchy equations and circuit ODEs](../concepts/euler-cauchy-higher-order-and-circuit-odes.md) first.

## Q8(a) Third-order Euler–Cauchy equation

> Solve \((x^3D^3+2xD-2)y=x^2\ln x+3x\).

Here \(D=d/dx\), so the equation is

\[
x^3y'''+2xy'-2y=x^2\ln x+3x,\qquad x>0.
\]

### Concept map

Matching powers \(x^3y'''\), \(xy'\), and \(y\) identify an Euler–Cauchy equation. First find CF by trying \(y=x^m\). Then find a PI for each forcing term.

### Detailed answer

For the homogeneous equation,

\[
x^3y'''+2xy'-2y=0,
\]

try \(y=x^m\). [Power rule: \(d(x^m)/dx=mx^{m-1}\).]

\[
y'=mx^{m-1},
\]

\[
y'''=m(m-1)(m-2)x^{m-3}.
\]

Substitute:

\[
x^3m(m-1)(m-2)x^{m-3}+2x(mx^{m-1})-2x^m=0.
\]

\[
\bigl[m(m-1)(m-2)+2m-2\bigr]x^m=0.
\]

The auxiliary equation is

\[
m(m-1)(m-2)+2m-2=0,
\]

\[
m^3-3m^2+2m+2m-2=0,
\]

\[
m^3-3m^2+4m-2=0,
\]

\[
(m-1)(m^2-2m+2)=0.
\]

Thus

\[
m=1,\qquad m=1\pm i.
\]

So

\[
\text{CF}=x\bigl(C_1+C_2\cos(\ln x)+C_3\sin(\ln x)\bigr).
\]

For a particular integral, use \(\theta=xD\). The operator polynomial is

\[
F(\theta)=\theta(\theta-1)(\theta-2)+2\theta-2.
\]

For \(x^2\ln x\), write \(s=\ln x\). Then \(\theta=x\,d/dx=d/ds\), so the same operator can be written \(F(D_s)\), and \(x^2\ln x=e^{2s}s\). Try

\[
y_{p1}=e^{2s}(As+B)=x^2(A\ln x+B).
\]

When an operator \(F(D_s)\) acts on \(e^{2s}v(s)\), the exponential can be kept outside and \(D_s\) is replaced by \(D_s+2\). Since \(v=As+B\), \(D_sv=A\) and \(D_s^2v=0\). Thus

\[
F(D_s+2)(As+B)=F(2)(As+B)+F'(2)A.
\]

Here

\[
F(2)=2,
\qquad F'(m)=3m^2-6m+4,
\qquad F'(2)=4.
\]

To produce \(e^{2s}s\), match coefficients:

\[
2(As+B)+4A=s.
\]

The coefficient of \(s\) gives \(2A=1\), so \(A=1/2\). The constant term gives \(2B+4A=0\), so \(2B+2=0\) and \(B=-1\). Therefore

\[
\text{PI}_1=x^2\left(\frac12\ln x-1\right).
\]

For \(3x=3e^s\), \(F(1)=0\), so a plain trial \(Ke^s\) would be killed by the operator. Multiply by \(s\) and try \(y_{p2}=Ke^ss=Kx\ln x\). Since \(F'(1)=1\),

\[
F(D_s+1)(Ks)=F(1)(Ks)+F'(1)K=K.
\]

To produce \(3e^s\), choose \(K=3\). Hence

\[
\text{PI}_2=3x\ln x.
\]

Therefore

\[
\boxed{y=x\bigl(C_1+C_2\cos\ln x+C_3\sin\ln x\bigr)+x^2\left(\frac12\ln x-1\right)+3x\ln x,\quad x>0.}
\]

## Q8(b) Current in an RL circuit

> Find the current \(i\) from \(L\frac{di}{dt}+Ri=E\sin2t\), where \(L,R,E\) are constants subject to \(i=0\) when \(t=0\).

### Concept map

This is a first-order linear ODE in \(i(t)\). Divide by \(L\), find an integrating factor, integrate, then use \(i(0)=0\).

### Detailed answer

Divide by \(L\):

\[
\frac{di}{dt}+\frac{R}{L} i=\frac{E}{L}\sin2t.
\]

The integrating factor is

\[
I=e^{\int(R/L)dt}=e^{Rt/L}.
\]

Multiply throughout:

\[
e^{Rt/L}\frac{di}{dt}+\frac{R}{L} e^{Rt/L}i=\frac{E}{L} e^{Rt/L}\sin2t,
\]

\[
\frac d{dt}\left(e^{Rt/L}i\right)=\frac{E}{L} e^{Rt/L}\sin2t.
\]

Let \(a=R/L\). Integrate:

\[
e^{at}i=\frac{E}{L}\int e^{at}\sin2t\,dt+C.
\]

[Formula: \(\int e^{at}\sin bt\,dt=e^{at}(a\sin bt-b\cos bt)/(a^2+b^2)\).]

\[
e^{at}i=\frac{E}{L}\frac{e^{at}(a\sin2t-2\cos2t)}{a^2+4}+C.
\]

At \(t=0\), \(i=0\), \(\sin0=0\), \(\cos0=1\):

\[
0=\frac{E}{L}\frac{-2}{a^2+4}+C,
\]

\[
C=\frac{2E}{L(a^2+4)}.
\]

Thus

\[
i=\frac EL\frac{a\sin2t-2\cos2t+2e^{-at}}{a^2+4}.
\]

Replace \(a=R/L\) and simplify:

\[
\boxed{i(t)=\frac{E\bigl(R\sin2t-2L\cos2t+2Le^{-Rt/L}\bigr)}{R^2+4L^2}.}
\]

At \(t=0\), its numerator is \(E(0-2L+2L)=0\), so the initial condition is satisfied.
