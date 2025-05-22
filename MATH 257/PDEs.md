- The order of a PDE is the value of the highest order partial derivative occurring in the equation
- The degree is the power of the highest derivative
- $Au_{xx}+Bu_{xy}+Cu_{yy}+Du_{x}+Eu_{y}+Fu=G$ is a second order liner PDE, the PDE is said to be homogeneous if $G=0$ 
- Analogous to characterizing quadratic equations $AX^{2}+BXY+CY^{2}+DX+EY=k$ as hyperbolic, parabolic or elliptic, determined by the sign of $\Delta=B^{2}-4AC$
	- $\Delta>0$: Hyperbolic, example $u_{tt}=c^{2}u_{xx}$  **wave equation
	- $\Delta=0$: Parabolic, example $u_{t}=u_{x x}$,  **heat/diffusion equation
	- $\Delta<0$: Elliptic, example $u_{x x}+u_{yy}=f$, **Laplace's equation** if $f=0$, otherwise **Poisson equation**
- Given the flux density relationship $\frac{ \partial u }{ \partial t }+c\frac{ \partial u }{ \partial x }=0$, we can guess the solution $u(x,t)=e^{at+bx}$
- Plug this into the equation to get $e^{at+bx}(a+c b)=0$
# Numerical (finite difference method)
- Approximating derivatives with difference operators 
- Recall that $f'(x)=\lim_{ x \to 0 } \frac{f(x+\Delta x)-f(x)}{\Delta x}$
- Then we can approximate the derivative to $f'(x)\approx \frac{f(x+\Delta x)-f(x)}{\Delta x}$ with a sufficiently small $\Delta x$
- Using the Taylor series we can say that $f(x+\Delta x)=f(x)+\Delta f'(x)+\frac{\Delta x^{2}}{2}f''(x)+\dots$
- $f(x-\Delta x)=f(x)-\Delta xf'(x)+\frac{\Delta x^{2}}{2}f''(x)+\dots$
- If we subtract the two equations we get $f(x+\Delta x)-f(x-\Delta x)=2\Delta xf'(x)+\frac{2\Delta x^{3}}{3!}+\dots$
- So we can get the approximate error of the derivative, the following is called a central difference scheme
- $f'(x)=\frac{f(x+\Delta x)-f(x)}{\Delta x}+0(\Delta x)^{2}$, this is second order accurate
- $f'(x)-\frac{f(x+\Delta x)-f(x)}{\Delta x}-0\Delta x$, this is a forward scheme and is first order accurate
- Now we can sum up the two equations and make $f''$ the subject
- $f(x+\Delta x)+f(x-\Delta x)=2f(x)+\frac{2\Delta x^{2}}{2}f''(x)+\dots$
- Then we get $f''(x)=\frac{f(x+\Delta x)-2f(x)+f(x-\Delta x)}{\Delta x^{2}}+0(\Delta x)^{2}$, central difference scheme for $f''$
# $1$D Heat Equation
- The heat equation is given by $u_{t}=\alpha u_{x x}$
- We need the boundary conditions for the $x$ domain and we need the initial conditions
- For example the Dirichlet $u(0,t)=A, u(h,t)=B$
- The Neumen boundary conditions $u_{x}(0,t)=A, u_{x}(L,t)=B$
- The Robin type conditions $u(0,t)+u_{x}(0,t)=A$
- Now we will solve an example
- $u_{t}=a^{2}u_{x x}$
- Boundary Condition: $u(0,t)=0, \quad u(L,t)=0, \quad u(x,0)=f(x)$
- **Step 1** Now it is time to discretize, given the domain of $x$ ranging from $0\to L$
- We split it into $n$ components where $x_{0}=0$ and $L=x_{n}$
- Now we do the same with $t$ splitting into $k$ components
- So $x_{n+1}-x_{n}=\Delta x$ and $t_{k+1}-t_{k}=\Delta k$
- **Step 2** Discretize the PDE
- Approximate $u_{t}$ with first forward difference and $u_{x x}$ with central difference scheme
- $u_{n}^{k}=u(x_{n},t_{k})$
- So now we have $\frac{u_{n}^{k+1}-u_{n}^{k}}{\Delta t}=\alpha^{2}\left[ \frac{u_{n+1}^{k}-2u_{n}^{k}+u_{n-1}^{k}}{\Delta x^{2}} \right]$
- Rearrange the equation to get $u_{n}^{k+1}=(1-2r)u_{n}^{k}+ru_{n+1}^{k}+ru_{n-1}^{k}$ where $r=\frac{\alpha^{2}\Delta t}{\Delta x^{2}}$
$\begin{bmatrix}u_{0} \\ u_{1} \\.\\.\\.\\u_{N}\end{bmatrix}^{k+1}=\begin{bmatrix}r & 1-2r & r &0&0&\dots \\ 0 &r & 1-2r  &r & 0 & \dots\\ . &.&.&.&. \\ .&. &.&.&.\\.&.&.&.&.\end{bmatrix}\begin{bmatrix}u_{0}\\.\\.\\.\\.\\u_{N}\end{bmatrix}^{k}$
- $u(0,t)=0\implies u_{0}^{k}=0$
- Therefore by recursive protocol $u_{0}^{k+1}=u_{0}^{k}=0$



