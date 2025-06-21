$\begin{cases}y''+\lambda y=0\\y(0)=0=y(L)\end{cases}\implies\lambda=\left( \frac{n\pi}{L} \right)^{2},\quad y(x)=\sin\left( \frac{n\pi}{L}x \right)$
$\begin{cases}y''+\lambda y=0\\y'(0)=0=y'(1)\end{cases}\implies \begin{cases}\lambda=\left( \frac{n\pi}{L} \right)^{2}\\y(x)=\cos\left( \frac{n\pi}{L}x \right)\end{cases}$
Every nice function can be written as a $f(x)=\sum_{n=0}^{\infty}c_{n}y_{n}(x)$
$\int_{0}^{L} y_{n}(x)y_{m}(x) \, dx=0$ if $m\neq n$
>[!Definition]
>$\mathcal{L}y=-\frac{d}{dx}\left( p(x)\frac{ d y }{ d x } \right)+q(x)y(x)$  The SL form
>$=-\left( \frac{ d P }{ d x }\cdot \frac{ d y }{ d x }+p(x)\frac{ d ^{2}y }{ d x^{2} } \right)+q(x)y(x)$
>Assume:$P$ is continuous diff, $q(x)$ is continuous and $r(x)$ is continuous

SL problem: $\mathcal{L}y=\lambda r(x)y$
$\alpha_{1} y(0)+\alpha_{2}y'(0)=0$
$\beta_{1}y(L)+\beta_{2}y'(L)=0$
$\alpha_{1},\alpha_{2},\beta_{1},\beta_{2}\in\mathbb{R}$
$\alpha_{1}$ or $\alpha_{2}\neq_{0}$
$\beta_{1}$ or $\beta_{2}\neq_{0}$

# Examples 1
## 1
$P\equiv 1,q\equiv 0, r\equiv1$
$\alpha_{2}=\beta_{2}=0$
$\begin{cases}\frac{ d ^{2}y }{ d x^{2} }+\lambda y=0\\y(0)=0\\y(L)=0\end{cases}$

## 2
$P\equiv1,q\equiv 0,r\equiv -1$
$\alpha_{1}=\beta_{1}=0$
$\begin{cases}y''+\lambda y=0\\y'(0)=y'(L)=0\end{cases}$

# Not SL
[[PDEs#Periodic|Periodic]] boundary conditions are not SL problems
e.g. $y''+\lambda y=0$
$y(0)=y(L)$
$y'(0)=y'(L)$

# Examples 2

$P_{0}(x)y''+P_{1}(x)y'+P_{2}(x)y+\lambda R(x)y=0$
$P_{0}(x)\neq{0}$ on $[0,L]$
$P_{i}$ is continuous 
$y''+\frac{P_{1}}{P_{0}}y'+\frac{P_{2}}{P_{0}}y+\lambda\frac{ R}{P_{0}}y=0$
$y''+a(x)y'=\frac{d}{dx}(p(x)y')$
$\hat{P}(x)=e^{\int \frac{P_{1}}{P_{2}}dx}$
$\implies-\frac{d}{dx}(-\hat{P}(x)y')+\hat{P} \frac{P_{2}}{P_{0}}y=-\lambda \hat{P} \frac{R}{P_{0}}y$
$P(x)=-\hat{P}(x)$
$q(x)=\hat{P} \frac{P_{2}}{P_{0}}$
$r(x)=-\hat{P} \frac{R}{P_{0}}$

## Example 1
$\phi''+x\phi'+\lambda \phi=0$
$e^{\int xdx}=e^{\frac{x^{2}}{2}}$
$-\frac{d}{dx}(-e^{\frac{x^{2}}{2}}\phi')=-\lambda e^\frac{x^{2}}{2}\phi$
$P(x)=-e^{\frac{x^{2}}{2}}$
$q(x)=0$
$r(x)=e^{\frac{-x^{2}}{2}}$

## Example 2
$-y''+x^{4}y'=\lambda y$
$\implies y''-x^{4}y=-\lambda y$
$e^{-\int x^{4}dx}=e^{\frac{x^{5}}{5}}$
$-\frac{d}{dx}(-e^{\frac{-x^{5}}{5}}y')=-\lambda e^{\frac{-x^{5}}{5}}y$


# Regular SL Problem
If $L<\infty,P>0,r>0$ on $[0,L]$
then $\mathcal{L}y=\lambda ry$ is a regular SL problem
Otherwise it is a singular SL problem

## Properties of regular SL
### Eigenvalues
**I** All eigenvalues are real
**II** There are infinitely many eigenvalues, can be written as 
$\lambda_{0}<\lambda_{1}<\lambda_{2},\dots\to \infty$
**III** If $\frac{\alpha_{1}}{\alpha_{2}}<0$,$\frac{\beta_{1}}{\beta_{2}}>0$ and $q_{1}>0$ on $[0,L]$ then $\lambda_{0}>0$
### Eigenfunctions
**I** For each $\lambda$, there is a unique ( up to rescaling ) $\phi_{j}$ solution to SL problem
**II** $\phi$ can be taken to be real valued, can be normalized to satisfy $\int_{0}^{L} \phi^{2}_{j}(x)r(x) \, dx=1$
**III** If $i\neq j$ then $\int_{0}^{L} \phi_{j}\phi_{i}r \, dx=0$, orthogonality
**IV** $\phi_{j}$ has exactly $j$ zeros on $(0,L)$ *In notes says $j-1$ zeros because of indexing*
**V** Collection of all $\phi_{j}$ is a spanning set i.e. if the [[Functions|function]] $f:[0,L]\to \mathbb{R}$ is nice enough then $\exists c_{j}\in \mathbb{R}$ s.t. $f(x)=\sum_{j=0}^{\infty}c_{j}\phi(x)$
Using orthogonality we can find out what $c_{j}$ has to be
$\int_{0}^{L} f(x)\phi_{k}(x)r(x) \, dx=\sum_{j=0}^{\infty}c_{j}\int_{0}^{L} \phi_{j}\phi_{k}r \, dx=c_{k}\int_{0}^{L}\phi_{k}^{2}r  \, dx$
So $c_{k}=\frac{ \int_{0}^{L} f(x)\phi_{k}(x)r(x) \, dx }{\int_{0}^{L}\phi_{k}^{2}(x)r(x)  \, dx}$

# Langrage's Identity
$\int_{0}^{L} v\mathcal{L}u-u\mathcal{L}v \, dx=-P(u'v-uv')\mid_{0}^{L}$
$\int_{0}^{L} v\mathcal{L}u \, dx=\int_{0}^{L} v\left[ -\frac{d}{dx}\left( p(x)\frac{ d u }{ d x } \right)+qu \right] \, dx$
$=-\int_{0}^{L} v \frac{d}{dx}\left( p \frac{ d u }{ d x } \right) \, d+\int_{0}^{L} quv \, dx$
$=-[vpu']^{L}_{0}\int_{0}^{L} \frac{dv}{dx}p\frac{ d u }{ d x } \, dx+\dots$
$=-vpu'\mid_{0}^{L}+p \frac{dv}{dx}\cdot u\mid_{0}^{L}$
AAAAAAAAAAAAAAA Im not writing this all down, look it up online
So if $u,v$ satisfies the boundary conditions
$\int_{0}^{L} u\mathcal{L}v \, dx=\int_{0}^{L} v\mathcal{L}u \, dx$
A linear operator that satisfies this identity is called symmetric

# Real examples
## Example 1
Consider $(xy')'+\frac{2}{x}y=-\lambda  \frac{1}{x}y$
$y'(1)=y'(2)=0$
First we expand the first term $xy''+xy'+\frac{2}{x}y=-\lambda  \frac{1}{x}y$
$\implies x^{2}y''+xy'+(\lambda+2)y=0$
$y=x^{r}$
$(r(r-1)+r+(\lambda+2))y=0$
$r=\pm \sqrt{ -(\lambda+2) }$
Case **I** $\lambda+2<0$, $y(x)=A^{\sqrt{ -(\lambda+2) }}+B^{-\sqrt{ -(\lambda+2) }}$
Case **II** $\lambda+2=0$, $y(x)=A+B\ln(x)$
$y'(1)=0=\frac{B}{x}\implies B=0$
$y=A$
Case **III** $\lambda+2>0$ $y(x)=A\cos(\sqrt{ \lambda+2 }\ln x)+B\sin(\sqrt{ \lambda+2 }\ln x)$
$y'=-\frac{A}{x}\sqrt{ \lambda+2 }\sin(\sqrt{ \lambda+2 }\ln x)+\frac{B}{x}\sqrt{ \lambda+2 }\cos(\sqrt{ \lambda+2 }\ln x)$
$y'(1)=B\sqrt{ \lambda+2 }=0\implies B=0$
$y'(2)=-\frac{A\sqrt{ \lambda+2 }}{2}\sin(\sqrt{ \lambda+2 }\ln 2)$
$\sqrt{ \lambda+2 }=\frac{n\pi}{\ln 2}$
$\lambda_{n}=\left( \frac{n\pi}{\ln 2} \right)^{2}-2,\quad n=0,1,2,\dots$
$y_{n}=\cos\left( \frac{n\pi}{\ln 2}\ln x \right)$
Recall that $r(x)=\frac{1}{x}$
$\int_{1}^{2} \cos\left( \frac{n\pi}{\ln 2}\ln x \right)\cos\left( \frac{m\pi}{\ln 2}\ln x \right)\cdot \frac{1}{x} \, dx$
Let $z=\frac{\pi}{\ln 2}\ln x$
$dz=\frac{\pi}{\ln 2}\cdot \frac{dx}{x}$
So then we have $\frac{\ln 2}{\pi}/\int_{0}^{\pi} \cos(nz)\cos(mz) \, dz$
$=\frac{\ln 2}{\pi}\cdot \frac{\pi}{2}\delta_{mn}=\frac{\ln 2}{2}\delta_{mn}$
$\begin{cases}\delta_{mn}=1 \text{ if }n = m \\\delta_{mn} =0\text{ if}n\neq m\end{cases}$
$f(x)=\sum_{n=0}^{\infty}c_{n}\cos\left( \frac{n\pi}{\ln 2}\ln x \right)$
$\int_{1}^{2} f(x)\cos\left( \frac{n\pi}{\ln 2}\ln x \right)\cdot \frac{1}{x} \, dx$
$=\sum_{n=0}^{\infty}c_{n}\int_{1}^{2} \cos\left( \frac{n\pi}{\ln 2}\ln x \right)\cos\left( \frac{m\pi}{\ln 2}\ln x \right) \, \frac{dx}{x}$
$=\frac{c_{k}(\ln 2)}{2}$
$c_{k}=\frac{2}{\ln 2}\int_{1}^{2} f(x)\cos\left( \frac{k\pi}{\ln 2}\ln x \right) \, \frac{dx}{x}$
