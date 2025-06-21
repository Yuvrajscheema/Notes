[[PDEs|Laplace equation]] arises as a steady state problem from when the heat or wave equation that do not vary with time so $\frac{ \partial u }{ \partial t }=0=\frac{ \partial^{2}u }{ \partial t^{2} }$, in 2D the equation reads $\nabla u=\frac{ \partial^{2}u }{ \partial x^{2} }+\frac{ \partial^{2}u }{ \partial y^{2} }=0$
# Rectangular Domain
## Dirichlet
$u_{x x}+u_{y y}=0\quad 0<x<a,\quad 0<y<b$
$u(0,y)=g_{1}(y),\quad u(a,y)=g_{2}(y)$
$u(x,0)=f_{1}(x),\quad u(x,b)=f_{2}(x)$

We cannot apply the method of separation of variables to this problem in its present form because, when we separate the variables, the boundary value problem must have homogeneous boundary conditions
We can address this difficulty by recognizing that the original problem is non homogeneous due to the four non-homogeneous BCs
The principle of superposition can be used here
To solve this we decompose the problem into four sub problems
$u(x,y)=u_{1}(x,y)+u_{2}(x,y)+u_{3}(x,y)+u_{4}(x,y)$
where each satisfies Laplace's equation with one non homogeneous boundary condition
Lets consider $u_{1}$
$u_{x x}+u_{yy}=0$
$u(0,y)=g_{1}(y)$
$u(a,y)=u(x,0)=u(x,b)=0$
We use separation of variables. We look for a solution of the form
$u(x,y)=X\cdot Y$
$X''Y+XY''$
$\frac{Y''}{Y}=-\frac{X''}{X}=\lambda$
Now lets consider $Y(y)$
$\begin{cases}Y''+\lambda Y=0\\Y(0)=0=Y(b)\end{cases}$
Then we get $Y_{n}=\sin\left( \frac{n\pi y}{b} \right),\quad\lambda_{n}\left( \frac{n\pi}{b} \right)^{2}$
Now we solve the equation $X''=\left( \frac{n\pi}{b} \right)^{2}X$
$X_{n}=A_{n}\cosh\left( \frac{n\pi x}{b} \right)+B_{n}\sinh\left( \frac{n\pi x}{b} \right)$
$X(a)=0$
$0=A_{n}\cosh\left( \frac{n\pi a}{b} \right)+B_{n}\sinh\left( \frac{n\pi a}{b} \right)$
So then $u_{n}=\left[ A_{n}\cosh\left( \frac{n\pi x}{b} \right) +B_{n}\sinh\left( \frac{n\pi x}{b} \right)\right]\sin\left( \frac{n\pi y}{b} \right)$
$u(0,y)=g_{1}(y)$
$g_{1}(y)=\sum_{n=1}^{\infty}A_{n}\sin\left( \frac{n\pi y}{b} \right)$
$A_{n}=\frac{2}{b}\int_{0}^{b} g_{1}(y)\sin\left( \frac{n\pi y}{b} \right) \, dy$
$B_{n}=-\frac{2}{b}\coth\left( \frac{n\pi a}{b} \right)\int_{0}^{b} g_{1}(y)\sin\left( \frac{n\pi y}{b}  \right) \, dy$
And then do the same for all of the other functions
## Neumann
Consider the following
$u_{x x}+u_{yy}=0,\quad 0<x<a,\quad 0<y<b$
$u_{y}(x,0)=0,\quad u_{y}(x,b)=0$
$u_{x}(0,y)=0,\quad u_{x}(a,y)=f(y)$
$u(x,y)=X(x)Y(y)$
$X''Y+XY''=0$
$\frac{X''}{X}=-\frac{Y''}{Y}=\lambda$
$Y''+\lambda Y=0$
$Y'(0)=Y'(b)=0$
The only non trivial solution is given by $\lambda_{n}=\left( \frac{n\pi}{b} \right)^{2}, n=0,1,2,\dots$
$Y_{n}=\cos\left( \frac{n\pi y}{b} \right)$
With this eigenvalue we get the following [[ODE Review|ODE]]
$X''-\left( \frac{n\pi}{b} \right)^{2}X=0$
So then we have $X_{n}=A_{n}\cosh\left( \frac{n\pi x}{b} \right)+B_{n}\sinh\left( \frac{n\pi x}{b} \right)$
We have the condition $X'(0)=0$ which gives us
$0=\frac{n\pi}{b}B_{n}\implies B_{n}=0$
So then $u_{n}=X_{n}Y_{n}=\cosh\left( \frac{n\pi x}{b} \right)\cos\left( \frac{n\pi y}{b} \right)$
Notice that for $n=0$ the solution is constant in $y$
Since Laplace's equation is linear the general solution is given by
$u(x,y)=\frac{c_{0}}{2}+\sum_{n=1}^{\infty}c_{n}\cosh\left( \frac{n\pi x}{b} \right)\cos\left( \frac{n\pi y}{b} \right)$
$u_{x}(a,y)=\sum_{n=1}^{\infty}c_{n} \frac{n\pi}{b}\sinh\left( \frac{n\pi a}{b} \right)\cos\left( \frac{n\pi y}{b} \right)=f(y)$
Now we can expand the function into the cosine series
$f(y)=\frac{1}{b}\int_{0}^{b} f(y) \, dy+\frac{2}{b}\sum_{n=1}^{\infty}\left[ \int_{0}^{b} f(y)\cos\left( \frac{n\pi y}{b} \right) \, dy \right]\cos\left( \frac{n\pi y}{b} \right)$
We cannot equate coefficients in the series for $f(y)$ since the first series has no constant term
Therefore we must have that $\int_{0}^{b} f(y) \, dy=0$
$c_{n}=\frac{2}{n\pi \sinh\left( \frac{n\pi a}{b} \right)}\int_{0}^{b} f(y)\cos\left( \frac{n\pi y}{b} \right) \, dy,\quad n\geq_{1}$
Note that the coefficient $c_{0}$ remains arbitrary, the solution $u$ is only determined up to an additive constant which is a feature of Neumann problems
## Mixed
Consider the following problem
$u_{x x}+u_{y y}=0\quad 0<x<a,\quad 0<y<b$
$u(0,y)=0,\quad u(a,y)=0$
$u(x,0)-u_{y}(x,0)=0,\quad u(x,b)=f(x)$
We want a solution of the form $y=XY$
$-\frac{X''}{X}=\frac{Y''}{Y}=\lambda$
We first solve the $X$ problem
$X''+\lambda X=0$
This gives us $\lambda_{n}=\left( \frac{n\pi}{a} \right)^{2},\quad X_{n}=\sin\left( \frac{n\pi x}{a} \right)\quad n=1,2,3$
Now lets look at $Y''-\left( \frac{n\pi}{a} \right)^{2}Y=0$
This gives us the solution $Y_{n}=A_{n}\cosh\left( \frac{n\pi y}{a} \right)+B_{n}\sinh\left( \frac{n\pi y}{a} \right)$
Since $u(x,0)-u_{y}(x,0)=0$ we must have that $Y_{n}(0)-Y'_{n}(0)=0$
Because $X_{n}\not\equiv{0}$
$Y_{n}(0)=A_{n},\quad Y'_{n}(0)=B_{n} \frac{n\pi}{a}$
$A_{n}=B_{n} \frac{n\pi}{a}$
$u_{n}=B_{n}\sin\left( \frac{n\pi x}{a} \right)\left[ \frac{n\pi}{a}\cosh\left( \frac{n\pi y}{a} \right)+\sinh\left( \frac{n\pi y}{a} \right) \right]$
$u(x,b)=f(x)=\sum_{n=1}^{\infty}B_{n}\sin\left( \frac{n\pi x}{a} \right)\left[ \frac{n\pi}{a}\cosh\left( \frac{n\pi b}{a} \right)+\sinh\left( \frac{n\pi b}{a} \right) \right]$
$f(x)=\sum_{n=1}^{\infty}C_{n}\sin\left( \frac{n\pi x}{a} \right)$
$A_{n}=\frac{2}{a}\int_{0}^{a} f(x)\sin\left( \frac{n\pi x}{a} \right) \, dx$
Equating the coefficients like sine functions we require
$B_{n}[\dots]=A_{n}$
$B_{n}=\left[ \frac{n\pi}{a}cos\left( \frac{n\pi b}{a}+\sinh\left( \frac{n\pi b}{a} \right) \right) \right]^{-1}\cdot \frac{2}{a}\int_{0}^{a} f(x)\sin\left( \frac{n\pi x}{a} \right) \, dx$
# Laplaces equation on a disk
Let $\Omega=\{ (x,y)]\in \mathbb{R}^{2}:x^{2}+y^{2}<a^{2} \}$
$u_{xx}+u_{yy}=0\quad (x,y)\in \Omega$
$u=h(\theta)\quad (x,y)\in \partial\Omega$
To solve we write this equation in polar coordinates as follows. To transform our equation in to polar coordinates we will write the operators $\partial _x$ and $\partial_{y}$ in polar coordinates
$x^{2}+y^{2}=r^{2}$
$\frac{y}{x}=\tan \theta$
Consider a function $u$ such that $u=u(r,\theta)$ where $r$ and $\theta$ are functions of $x,y$
$\frac{ \partial  }{ \partial x }u(r(x,y),\theta(x,y))=u_{r}r_{x}+u_{\theta}\theta_{x}$
$=u_{r}\cos \theta-\frac{{\sin \theta}}{r}u_{\theta}$
Therefore $\frac{ \partial  }{ \partial x }=\cos \theta \frac{ \partial  }{ \partial r }-\frac{{\sin \theta}}{r}\frac{ \partial  }{ \partial \theta }$
and $\frac{ \partial  }{ \partial y }=\sin \theta \frac{ \partial  }{ \partial r }+\frac{{\cos \theta}}{r}\frac{ \partial  }{ \partial \theta }$
Squaring and adding both of these operators gives the following
$\frac{ \partial^{2}  }{ \partial x^{2} }+\frac{ \partial^{2} }{ \partial y^{2} }=\frac{ \partial^{2} }{ \partial r^{2} }+\frac{1}{r}\frac{ \partial  }{ \partial r }+\frac{1}{r^{2}}\frac{ \partial^{2} }{ \partial \theta^{2} }$
So now let Laplace's equation in polar coordinates be given by
$u_{rr}+\frac{1}{r}u_{r}+\frac{1}{r^{2}}u_{\theta \theta}\quad 0<r<a,\quad_{0}\leq \theta\leq{2}\pi$
$u(a,\theta)=h(\theta)$
It is implied that $u(r,2\pi)=u(r,0)$ and $u_{\theta}(r,0)=u_{\theta}(r,2\pi)$
We separate teh variables to get $y=R\Theta$
This gives us $R''\Theta+\frac{1}{r}R'\Theta+\frac{1}{r^{2}}\Theta''=0$
Rearrange this to get $r^{2} \frac{R''}{R}+r \frac{R'}{R}+\frac{\Theta''}{\Theta}=0$
$\frac{\Theta''}{\Theta}=-\left( r^{2} \frac{R''}{R}+r \frac{R'}{R} \right)=\lambda$
$\Theta''-\lambda\Theta=0$
So then with the implied condition we have $\Theta_{n}=A_{n}\cos(n\theta)+B_{n}\sin(n\theta),\quad \lambda_{n}=-n^{2},\quad n=0,1,2,\dots$
So then for $R$ we have $r^{2}R''+rR'-n^{2}R=0$
Assume the solution $R=r^{\alpha}$
This gives us $\alpha^{2}-n^{2}=0$
Thus we have two distinct solutions $\alpha=\pm n$ when $n$ is positive and one double root $\alpha=0$
$\begin{cases}R_{n}=C_{n}r^{n}+D_{n}r^{-n} &  \text{for } n>0\\R_{0}=C_{0}+D_{0}\ln r & \text{for } n=0 \end{cases}$
Since the radical function $R$ must be bounded at the origin, we are forced to set all values $D's$ to vanish and the general solution becomes $R=r^{n},\quad n\geq_{0}$
$u_{n}=r^{n}[A_{n}\cos(n\theta)+B_{n}\sin(n\theta)]$
Now we satisfy the boundary condition
$u(a,\theta)=h(\theta)=\sum_{n=0}^{\infty}a^{n}[A_{n}\cos n\theta+B_{n}\sin(n\theta)]$
Using the orthogonality of the trigonometric functions on $[0,2\pi]$ the [[Fourier Series|Fourier]] coefficients are determined by:
$A_{0}=\frac{1}{2\pi}\int_{0}^{2\pi} h(\phi) \, d\phi,\quad A_{n}=\frac{1}{\pi a^{n}}\int_{0}^{2\pi} h(\phi)\cos(n\phi) \, d\phi$
$B_{n}=\frac{1}{na^{n}}\int_{0}^{2\pi} h(\phi)\sin(n\pi) \, d\phi,\quad n=1,2,\dots$
Using some trig identities this can be written as
$u(r,\theta)=\frac{1}{2\pi}\int_{0}^{2\pi} h(\phi)\left[ 1+2\sum_{n=1}^{\infty}\left( \frac{r}{a} \right)^{n}\cos(n(\theta-\phi)) \right] \, d\phi$
This has a geometric series, using that fact we get
$u(r,\theta)=\frac{1}{2\pi}\int_{0}^{2\pi} h(\phi) \frac{{a^{2}-r^{2}}}{a^{2}-2ar\cos(\theta-\phi)+r^{2}} \, d\phi$
# Semi Infinite Strip
$u_{x x}+u_{yy}=0,\quad 0<x<a,\quad 0<y<\infty$
Consider the following boundary conditions
$u(0,y)=0=u(a,y)$
$u(x,0)=f(x),\quad u(x,y)\to0$ as $y\to \infty$
$u=XY$
$\frac{X''}{X}=-\frac{Y''}{Y}=\lambda$
$X''-\lambda X=0$
$\lambda_{n}=-\left( \frac{n\pi}{a} \right)^{2},\quad X_{n}=\sin\left( \frac{n\pi x}{a} \right),\quad n=1,2,3,\dots$
$Y''-\left( \frac{n\pi}{a} \right)^{2}Y=0$
$Y=A_{n}e^{\frac{-n\pi}{a}y}+B_{n}e^{\frac{-n\pi}{a}y}$
Since $u(x,y)\to0$ as $y\to \infty$
We have that $Y=A_{n}e^{\frac{-n\pi}{a}y}$
$u_{n}=c_{n}e^{\frac{-n\pi}{a}y}\sin\left( \frac{n\pi}{a}x \right)$
$u(x,0)=f(x)=\sum_{n=1}^{\infty}c_{n}\sin\left( \frac{n\pi x}{a} \right)$
$c_{n}=\frac{2}{a}\int_{0}^{a} f(x)\sin\left( \frac{n\pi x}{a} \right) \, dx$
## Non homegeneous Boundary
$u_{x x }+u_{yy}=0,\quad 0<x<a,\quad 0<y<\infty$
$u(0,y)=a,\quad u(a,y)=B$
$u(x,0)=f(x),\quad u(x,y)\to 0$ as $y\to \infty$
We seek a function $v(x)$ such that $v''=0$ and it satisfies the inhomogeneous boundary conditions
The general solution is of the form $v=\alpha x+\beta$
In this case we have $v=\frac{B-A}{a}x+B$
$u(x,y)=v(x)+w(x,y)$
So then we have the following PDE
$w_{x x}+w_{yy}=0$
$w(0,y)=0,\quad w(a,y)=0$
$w(x,0)=f(x)-v(x)$
We already have solved this kind of question
$w(x,y)=\sum_{n=1}^{\infty}d_{n}e^{-\frac{n\pi}{a}y}\sin\left( \frac{n\pi x}{a} \right)$
So then $d_{n}=\frac{2}{a}\int_{0}^{a} [f(x)-v(x)]\sin\left( \frac{n\pi x}{a} \right) \, dx$
