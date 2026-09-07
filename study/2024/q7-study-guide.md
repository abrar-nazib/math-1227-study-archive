# Math 1227 — 2024 Q7 study guide

Read [First-order ODEs](../concepts/first-order-odes-exact-integrating-factors-and-substitutions.md) first.

## Q7(a) Exact differential equation and a source issue

> What is exact differential equation? Find the general solution of \((12y+4x^3+6x^2)dx+3(x+xy^2)dy=0\).

An equation \(Mdx+Ndy=0\) is exact when \(M_y=N_x\). For the transcription in the paper,

\[
M=12y+4x^3+6x^2,\qquad N=3x+3xy^2.
\]

Then

\[
M_y=12,
\qquad N_x=3+3y^2.
\]

These are not equal for general \(y\), so the printed equation is **not exact as transcribed**. It also does not meet the standard one-variable integrating-factor tests. Because the source scan that produced this transcription is not available in the repository, a correction would be guesswork. I have deliberately not invented one. Please provide the original Q7(a) scan or confirm the equation before this part is solved.

> [!IMPORTANT]
> **Exam definition — exact differential equation**
>
> An equation \(M(x,y)dx+N(x,y)dy=0\) is exact if there exists a function \(\Phi(x,y)\) such that \(d\Phi=Mdx+Ndy\). Equivalently, on a suitable region, \(M_y=N_x\).

## Q7(b) Nonlinear equation made linear by \(u=\tan y\)

> Solve \(\frac{dy}{dx}+x\sin2y=x^3\cos^2y\).

### Concept map

The repeated trigonometric package suggests dividing by \(\cos^2y\), then using \(u=\tan y\). This turns the equation into a first-order linear ODE.

### Detailed answer

Start with

\[
\frac{dy}{dx}+x\sin2y=x^3\cos^2y.
\]

Divide by \(\cos^2y\):

\[
\sec^2y\frac{dy}{dx}+x\frac{\sin2y}{\cos^2y}=x^3.
\]

Use \(\sin2y=2\sin y\cos y\):

\[
\frac{\sin2y}{\cos^2y}=\frac{2\sin y\cos y}{\cos^2y}=2\tan y.
\]

Let \(u=\tan y\). [Chain rule: \(du/dx=\sec^2y\,dy/dx\).] Then

\[
\frac{du}{dx}+2xu=x^3.
\]

This is linear. Its integrating factor is

\[
I=e^{\int2x\,dx}=e^{x^2}.
\]

Multiply throughout:

\[
e^{x^2}\frac{du}{dx}+2xe^{x^2}u=x^3e^{x^2},
\]

\[
\frac{d}{dx}\bigl(e^{x^2}u\bigr)=x^3e^{x^2}.
\]

Integrate. Put \(v=x^2\), so \(dv=2x\,dx\) and \(x^3dx=x^2(xdx)=v\,dv/2\):

\[
e^{x^2}u=\int x^3e^{x^2}dx+C
=\frac12\int ve^v dv+C.
\]

[Integration by parts: \(\int ve^v dv=ve^v-\int e^v dv=e^v(v-1)\).]

\[
e^{x^2}u=\frac12e^v(v-1)+C
=\frac12e^{x^2}(x^2-1)+C.
\]

Divide by \(e^{x^2}\):

\[
u=\frac{x^2-1}{2}+Ce^{-x^2}.
\]

Since \(u=\tan y\),

\[
\boxed{\tan y=\frac{x^2-1}{2}+Ce^{-x^2}}.
\]

## Q7(c) Integrating factor depending on \(y\)

> Find the integrating factor and hence find the general solution of \(y\ln y\,dx+(x-\ln y)dy=0\).

### Concept map

Write \(M=y\ln y\), \(N=x-\ln y\). It is not exact, but \((N_x-M_y)/M\) depends only on \(y\), so an integrating factor \(\mu(y)\) makes it exact. Since \(\ln y\) appears, work on \(y>0\).

### Detailed answer

\[
M=y\ln y,\qquad N=x-\ln y.
\]

Differentiate:

\[
M_y=\ln y+1,
\qquad N_x=1.
\]

Then

\[
\frac{N_x-M_y}{M}
=\frac{1-(\ln y+1)}{y\ln y}
=\frac{-\ln y}{y\ln y}
=-\frac1y.
\]

Therefore

\[
\mu(y)=e^{\int-1/y\,dy}=e^{-\ln y}=\frac1y.
\]

Multiply the whole equation by \(1/y\):

\[
\ln y\,dx+\left(\frac{x}{y}-\frac{\ln y}{y}\right)dy=0.
\]

This is exact because

\[
\frac{\partial(\ln y)}{\partial y}=\frac1y,
\qquad
\frac{\partial}{\partial x}\left(\frac{x}{y}-\frac{\ln y}{y}\right)=\frac1y.
\]

Integrate the first coefficient with respect to \(x\):

\[
\Phi=\int\ln y\,dx+g(y)=x\ln y+g(y).
\]

Differentiate with respect to \(y\):

\[
\Phi_y=\frac{x}{y}+g'(y).
\]

Match with the second coefficient:

\[
\frac{x}{y}+g'(y)=\frac{x}{y}-\frac{\ln y}{y},
\]

\[
g'(y)=-\frac{\ln y}{y}.
\]

Put \(w=\ln y\), so \(dw=dy/y\):

\[
g(y)=-\int w\,dw=-\frac12w^2=-\frac12(\ln y)^2.
\]

Thus

\[
\boxed{x\ln y-\frac12(\ln y)^2=C,\qquad y>0.}
\]
