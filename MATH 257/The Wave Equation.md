- We will explore the solution of the one dimensional wave equation on a finite domain
- The approach is similar to the heat equation with a couple key differences
- The time equation becomes a second order ODE with an indicial equation that yields complex roots resulting in time dependent functions that are sines and cosines, rather than the exponential decay found in the heat equation
- Depending on the boundary conditions applied to the spatial ODE, we derive eigenvalue problems that are analogous to those encountered in the heat equation. Each eigenfunction corresponds to a particular periodic extension of the solution. For instance Dirichlet boundary conditions lead to eigenfunctions that are sine functions, which are associated with the odd periodic extension of the solution defined on the domain $(0,L)$.
- We will also derive the classical D'Alembert Solution to the wave equation on the domain $(-\infty, +\infty)$
# Separation of variables
 $\frac{ \partial^{2}u }{ \partial t^{2} }=c^{2}\frac{ \partial^{2}u }{ \partial x^{2} }, \quad 0<x<L,\quad t>0$
 BC:   $u(0,t)=0, \quad u(L,t)=0$
 IC:    $u(x,0)=f(x)\quad u_{t}(x,0)=g(x)$
 This problem concerns wave propagation on a string of length L with fixed ends, meaning the displacement at both ends is zero.
 The function $u(x,t)$ represents the vertical displacement of the string as a function of time. The wave equation is derived under the assumptions that the displacement remains small and the string is uniform. The wave speed $c$ is given by $c=\sqrt{ \frac{\tau}{\mu} }$
Where $\tau$ represents the tension in the string and $\mu$ is the mass per unit length
This principle is evident in string instruments, by adjusting the tension, different tones can be produced, while the properties of the string-such as material and thickness also influence the sound.
A thicker string increases mass density, which in turn lowers the frequency
The term $u_{tt}$ represents the acceleration of a segment of the string, while $u_{x x}$ represents the concavity. A positive concavity indicates an upward curve, meaning adjacent points pull toward equilibrium.
To **solve** lets let $u(x,t)=X(x)T(t)$
This gives us $X\ddot{T}=c^{2}X''T$
$\frac{1}{c^{2}} \frac{\ddot{T}}{T}=\frac{X''}{X}=\lambda$
This leads to two equations, $\ddot{T}=c^{2}\lambda T,\quad X''=\lambda X$
The boundary conditions $X(0)=X(L)=0$ give us the solution:
$X_{n}(x)=\sin\left( \frac{n\pi x}{L} \right),\quad \lambda_{n}=-\left( \frac{n\pi}{L} \right)^{2},n=1,2,3,\dots$
The main difference from the solution of the heat equation is the form of the time equation which is a second order ODE
$T''+\left( \frac{n\pi c}{L} \right)^{2}T=0$
The solutions to this equation gives us $T_{n}(t)=A_{n}\cos\left( \frac{n\pi ct}{L} \right)+B_{n}\sin\left( \frac{n\pi ct}{L} \right)$
The general solution is a superposition of  all product solutions is
$u(x,t)=\sum_{n=1}^{\infty}\left[ A_{n}\cos\left( \frac{n\pi ct}{L} \right)+B_{n}\sin\left( \frac{n\pi ct}{L} \right) \right]\sin\left( \frac{n\pi x}{L} \right)$
Now we need to satisfy the initial conditions
$f(x)=u(x,0)=\sum_{n=1}^{\infty}A_{n}\sin\left( \frac{n\pi x}{L} \right)$
Hence, 
$A_{n}=\frac{2}{L}\int_{0}^{L} f(x)\sin\left( \frac{n\pi x}{L} \right) \, dx$
In order to obtain the solution on the initial velocity $u_{t}(x,0)=g(x)$, we need to differentiate the general solution with respect to $t$, this gives us
$g(x)=u_{t}(x,0)=\sum_{n=1}^{\infty} \frac{n\pi c}{L}B_{n}\sin\left( \frac{n\pi x}{L} \right)$
$B_{n}=\frac{2}{n\pi c}\int_{0}^{L} g(x)\sin\left( \frac{n\pi x}{L} \right) \, dx$
## Example 1
$L=1$
$\frac{ \partial^{2}u }{ \partial t^{2} }=c^{2}\frac{ \partial^{2}u }{ \partial x^{2} }$
$u(0,t)=u(1,t)=0$
$u(x,0)=x(1-x)$
$u_{t}(x,0)=0$
So we have $u(x,t)=\sum_{k=1}^{\infty}\sin(k\pi x)[A_{k}\cos(ck\pi t)+B_{k}\sin(ck\pi t)]$
This gives us the following
$A_{k}=2\int_{0}^{1} x(1-x)\sin(k\pi x) \, dx,\quad\quad B_{k}=0$
After integrating by parts we have that $A_{k}=\frac{3}{k^{3}\pi^{3}}[1-\cos(k\pi)]$
$=\begin{cases} \frac{8}{k^{3}\pi^{3}}  & \text{for k odd} \\ 0  & \text{for k even}\end{cases}$
So then we finally have $u(x,t)=\sum_{n=0}^{\infty} \frac{8}{(2n+1)^{3}\pi^{3}}\sin((2n+1)\pi x)\cos(c(2n+1)\pi t)$
## Example 2
$L=1$
$\frac{ \partial^{2}u }{ \partial t^{2} }=c^{2}\frac{ \partial^{2}u }{ \partial x^{2} }$
$u(0,t)=u(1,t)=0$
$u(x,0)=\sin(5\pi x)+2\sin(7\pi x),\quad \quad u_{t}(x,0)=0$
$u(x,t)=\sum_{k=1}^{\infty}\sin(k\pi x)[A_{k}\cos(ckn\pi t)+B_{k}\sin(ck\pi t)]$
$\sin(5\pi x)+2\sin(7\pi x)=u(x,0)=\sum_{k=1}^{\infty}A_{k}\sin(k\pi x)=\begin{cases}1  & \text{if }k=5 \\ 2 & \text{if } k=7 \\0 & \text{if }k \neq{5},7\end{cases}$
$B_{k}=0$
So then $u(x,t)=\sin(5\pi x)\cos(5c\pi t)+2\sin(7\pi x)\cos(7c\pi t)$

# Non-homogeneous
Consider the wave equation with a source
$u_{tt}=c^{2}u_{x x}+s(x,t)$
BC:    $u(0,t)=u(L,t)=0$
IC:     $u(x,0)=f(x),\quad u_{t}(x,0)=g(x)$
To solve this we first look for a particular solution $v(x,t)$
The general solution will be $u(x,t)=v(x,t)+w(x,t)$ where $w$ is the general solution of the homogeneous equation $u_{tt}=c^{2}u_{x x}$
## Steady state
If the source term $s(x,t)$ does not depend on time then we can look for $v(x,t)=v(x)$ not depending on time
The PDE becomes $0=c^{2}v''+s(x)$ and we must solve this subject to the boundary conditions $v(0)=v(L)=0$. In this case it can be solved by integrating twice

### Example
$u_{tt}=u_{x x}+x$
BC:  $u(0,t)=u(1,t)=0$
IC:  $u(x,0)=0,\quad u_{t}(x,0)=1$
Let $v(x)$ be the particular solution, then we have $0=v''+x$ so that gives us $v(x)=\frac{x^{3}}{6}+Ax+B$ after integrating twice
Plugging in the boundary conditions gives us $B=0$ and $A=\frac{1}{6}$
So $v(x)=\frac{x-x^{3}}{6}$
The other part of the solution satisfies $w_{tt}=w_{x x}$
The boundary conditions give us $w(0,t)=w(1,t)=0$
The initial conditions give us that $w(x,0)=-\frac{x-x^{3}}{6},\quad w_{t}(x,0)=1$
We use a [[Fourier Series]] to get $w(x,t)=\sum_{n=1}^{\infty}\sin(n\pi x)[a_{n}\cos(n\pi t)+b_{n}\sin(n\pi t)]$
Where:
$a_{n}=-\frac{1}{3}\int_{0}^{1} (x-x^{3})\sin(n\pi x) \, dx=\frac{2(-1)^{n}}{n^{3}\pi^{3}}$
$b_{n}=\frac{2}{n\pi}\int_{0}^{1} \sin(n\pi x) \, dx=\frac{2(1-(-1)^{n})}{n^{2}\pi^{2}}$
So the complete solution is given by $u(x,t)=\frac{x-x^{3}}{6}+\sum_{n=1}^{\infty} \left( \frac{2(-1)^{n}}{n^{3}\pi^{3}}\cos(n\pi t)+\frac{2(1-(-1)^{n})}{n^{2}\pi^{2}}\sin(n\pi t) \right)\sin(n\pi x)$

## Exponential in $t$
If the source term is a function of $x$ times a an exponential in $t$, we may look for a particular solution $v(x,t)$ that is also of this form
Consider the following equation
$u_{tt}=u_{ xx}+xe^{-t}$
BC:  $u(0,t)=u(1,t)=0$
IC:  $u(x,0)=0,\quad u_{t}(x,0)=1$
We look for a solution of the form $v(x,t)=V(x)e^{-t}$
Then the differential equation says that $V(x)e^{-t}=V''(x)e^{-t}+xe^{-t}$
The general solution of this differential equation is $V(x)=x+c_{1}e^{x}+c_{2}e^{-x}$
Using the boundary conditions and solving for $c_{1}$ and $c_{2}$ gives
$v(x,t)=\left( x-\frac{e^{1+x}}{e^{2}-1}+\frac{e^{1-x}}{e^{2}-1} \right)e^{-t}$
And then the initial conditions for $w$ are as follows
$w(x,0)=-v(x,0)=-V(x)=-x+\frac{e^{1+x}-e^{1-x}}{e^{2}-1}$
$w_{t}(x,0)=1-v_{t}(x,0)=1+V(x)=1+x-\frac{e^{1+x}-e^{1-x}}{e^{2}-1}$

## Arbitrary function of $x$ and $t$
We will use an eigenfunction expansion. We can write $u(x,t)$ and $s(x,t)$ for any $t$ as such a series obtaining series expansions where the coefficients are functions of $t$
$u(x,t)=\sum_{n=1}^{\infty}b_{n}(t)\phi_{n}(x)$
$s(x,t)=\sum_{n=1}^{\infty}c_{n}(t)\phi_{n}(x)$
Our PDE will give us the relation between these, which will be ordinary differential equations in $b_{n}(t)$ for each $n$
### Example
$u_{tt}=u_{x x}+xt$
$u(0,t)=u(1,t)=0$
$u(x,0)=0,\quad u_{t}(x,0)=1$
The appropriate eigenfunctions for the homogeneous problem are $\phi_{n}(x)=\sin(n\pi x)$, the expansion being the Fourier sine series on the interval $[0,1]$, in particular:
$xt=\sum_{n=1}^{\infty} \frac{2(-1)^{n+1}t}{n\pi}\sin(n\pi x)$
So $c_{n}(t)=\frac{2(-1)^{n+1}t}{n\pi}$ Putting these series into the differential equation we get
$\sum_{n=1}^{\infty}b_{n}''(t)\sin(n\pi x)=-\sum_{n=1}^{\infty}b_{n}(t)(n\pi)^{2}\sin(n\pi x)+\sum_{n=1}^{\infty}c_{n}(t)\sin(n\pi x)$
By the uniqueness of the Fourier series the coefficients for each $n$ must match
$b_{n}''=-(n\pi)^{2}b_{n}+c_{n}(t)=-(n\pi)^{2}b_{n}-\frac{2(-1)^{n}t}{n\pi}$
The initial conditions for $u$ and $u_{t}$ give us initial conditions for $b_{n}$ and $b'_{n}$
$u(x,0)=0\implies b_{n}(0)=0$
$u_{t}(x,0)=\sum_{n=1}^{\infty} \frac{2(1-(-1)^{n})}{n\pi}\sin(n\pi x)$ so $b'_{n}(0)= \frac{2(1-(-1)^{n})}{n\pi}$
The general solution for the differential equation for $b_{n}$ is 
$b_{n}(t)=A_{n}\cos(n\pi t)+B_{n}\sin(n\pi t)-\frac{2(-1)^{n}t}{(n\pi)^{3}}$
From the initial conditions we get $b_{n}(0)=0=A_{n}$ and $b'_{n}(0)=\frac{2(1-(-1)^{n})}{n\pi}=n\pi B_{n}-\frac{2(-1)^{n}}{(n\pi)^{3}}$
So the complete solution is given by
$u(x,t)=\sum_{n=1}^{\infty}\left[ \left(  \frac{2(-1)^{n}}{(n\pi)^{4}}+\frac{2(1-(-1)^{n})}{(n\pi)^{2}} \right)\sin(n\pi t)-\frac{2(-1)^{n}t}{(n\pi)^{3}} \right]\sin(n\pi x)$

# d'Almberts Solution
Only applies to homogeneous wave equation
$u_{tt}=c^{2}u_{x x}\quad-\infty<x<\infty$
Boundary conditions are not defined
$u(x,0)=f(x)\quad u_{t}(x,0)=g(x)$
$\xi=x+ct\quad \eta =x-ct$
$\frac{ \partial u }{ \partial x }=\frac{ \partial u }{ \partial \xi },\frac{ \partial u }{ \partial \eta }$
$u_{tt}-c^{2}u_{x x}=0$
$u_{\xi \zeta}=0$
$u(\xi,\eta)=F(\xi)+G(\eta)$
$u(x,t)=F(x+ct)+G(x-ct)$
$u(x,0)=f(x)=F(x)+G(x)$ **(1)**
$u_{t}(x,t)=cF'(x+ct)-cG'(x-ct)$
$u_{t}(x,0)=c[F'(x)-G'(x)]$ **(2)**
$\frac{1}{c}\int_{0}^{x} g(s) \, ds=F(x)-G(x) -[F(0)-G(0)]$ **(3)**
Add **(1)** and **(3)** together
$\frac{f(x)}{2}+\frac{1}{2c}\int_{0}^{x} g(s) \, ds=F(x)-C$
**(1)-(3)**
$\frac{f(x)}{2}-\frac{1}{2c}\int_{0}^{x} g(x) \, ds=G(x)+C$
$F(x+ct)=\frac{f(x+ct)}{2}+\frac{1}{2c}\int_{0}^{x+ct} g(s) \, ds$
$G(x-ct)=\frac{f(x-ct)}{2}-\frac{1}{2c}\int_{0}^{x-ct} g(s) \, ds$
$u(x,t)=\frac{1}{2}[f(x+ct)+f(x-ct)]+\frac{1}{2c}\int_{x-ct}^{x+ct}g(s)  \, ds$

## Example
$u_{tt}=u_{x x}$
$u(x,0)=\sin x\quad u_{t}(x,0)=x^{2}$
$u(x,t)=\frac{1}{2}[\sin(x+t)+\sin(x-t)]+\frac{1}{2}\int_{x-t}^{x+t}s^{2}ds$
