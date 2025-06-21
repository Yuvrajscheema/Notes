# 5.1 Linearization, critical points and equilibrium
- We focus on first order non linear autonomous systems of of the form $\vec{x} = f(\vec{x})$ where $f$ does not explicitly depend on $t$
- To find critical points we do $f = \vec{0}$
- More on critical points in [[Two Dimensional systems and their vector fields]]
## Linearization
- Lets consider a two dimensional system
- $\begin{bmatrix}x' \\ y'\end{bmatrix} = \begin{bmatrix} f(x,y) \\ g(x,y)\end{bmatrix}$
- Assume that $(x_{0},y_{0})$ is a critical point, we define the the deviation $u(t),v(t)$ as:
- $x = x_{0} + u$, $y = y_{0}+v$ so $u = x-x_{0}$ and $v = y - y_{0}$ where x $x$ and $y$ are the solution of the system
- We want to find the ODEs governing the variation of $u,v$ 
- Now there is a derivation using the taylor series however this does not concern us
>[!Definition]
>The linearization of a system is given by:
>$\begin{bmatrix} u' \\ v'\end{bmatrix} = J_{f}(x_{0},y_{0}) \begin{bmatrix} u \\ v\end{bmatrix}$
>Where $J_{f}$ is the Jacobian matrix evaluated at $(x_{0},y_{0})$ and defined by:
>$J_{f}(x_{0},y_{0}) = \begin{bmatrix} \frac{\partial f}{\partial x} (x_{0},y_{0}) & \frac{\partial f}{\partial y} (x_{0},y_{0}) \\ \frac{\partial g}{\partial x} (x_{0},y_{0}) & \frac{\partial g}{\partial y} (x_{0},y_{0})\end{bmatrix}$
>The linearization is an approximate solution of $\vec{x} = f(\vec{x})$

# Stability of critical points
- A critical point is isolated if it is the only critical point in some sufficiently small open rectangle in 2D
- A system at a critical point is almost linear if the critical point is isolated and the Jacobian matrix at the critical point is invertible i.e. $\det(J_{f}) \neq 0$
- A critical point is 
	- **Stable** if every real solution that starts with $\vec{x}(t=0)$ sufficiently close to the point remains arbitrarily close to it for all $t>0$
	- **Unstable** if at least one solution doesn't satisfy the above
	- **Asymptotically stable** if it is stable and every solution starts sufficiently close has $\lim_{ t \to \infty } \vec{x} = (x_{0},y_{0})$

# Examples
- $\begin{cases} x' = \sin (x+y) \\ y' = e^{x}-1\end{cases}$
- The critical points are $x=0$ $y = \pm n\pi$
- Linearization $\begin{bmatrix} \cos \pm \pi & \cos\pm n\pi \\ 1 & 0\end{bmatrix}$
- if even$\begin{bmatrix} 1 & 1 \\ 1 & 0\end{bmatrix}$ the eigenvalues are $\lambda_{+,-} = \frac{1}{2}(1\pm \sqrt{ 5 })$ saddle([[Two Dimensional systems and their vector fields#Case 3 distinct real, opposite signs|source]]) the eigenvectors are $v_{-} = \begin{bmatrix} \frac{1}{2}(1-\sqrt{ 5 })\\ 1\end{bmatrix}$ and $v_{_{+}} = \begin{bmatrix} \frac{1}{2}(1+\sqrt{ 5 })\\ 1\end{bmatrix}$
- if odd $\begin{bmatrix} -1 & -1 \\ 1 & 0\end{bmatrix}$ the eigenvalues are $\lambda = \frac{1}{2}(-1\pm i\sqrt{ 3 })$ spiral sink ([[Two Dimensional systems and their vector fields#Case 6 complex eigenvalues, Re($ lambda_{1}, lambda_{2}$) $<0$|source]])
- Direction $\begin{bmatrix} -1 & -1 \\ 1 & 0\end{bmatrix} \begin{bmatrix} 0\\ 1\end{bmatrix} = \begin{bmatrix} -1\\ 0\end{bmatrix}$ counterclockwise
- x nullcline $\sin(x+y) =0 \implies x+y=\pm \pi$
- y nullcline $e^{x}-1=0 \implies x=0$
- **Another example** 
- Conservative equations, there the energy is a conserved quantity
- $E(x,y)= \frac{1}{2}y^2+F(x)$
- $y$ "momentum abd $y=x'$ solutions are such that $E(x,y) = C$ 
- Differential equation? $\frac{d}{dt}E = 0$ apply the chain rule $F'+y' = 0$
- So we get $x''=-f(x)$ ; $f(x) = F'(x)$ "Newtons equation"
- Equivalently $\begin{cases} x' = y\\y' = -f(x)\end{cases}$ "Hamiltons Equation"
- Critical points are $y=0$ and $f(x) = 0$
- Take the Jacobian $J = \begin{bmatrix} 0 & 1 \\ -f'(x) & 0\end{bmatrix}$
- Eigenvalues are $\lambda^{2}+f'(x_{0}) = 0$ 
- Two possibilities: $f'(x_{0})>0$  then $\lambda=\pm i \sqrt{ f'(x_{0}) }$  **center**; $f'(x_{0})\leq_{0}$ then $\lambda = \pm \sqrt{ -f(x_{0}) }$  **saddle**
- Another Example!
- $x''+x-x^{2}=0 \Longleftrightarrow \begin{cases}x'=y \\  \\y' = x^2-x\end{cases}$ $f(x)=x-x^2$ $E(x,y) =\frac{1}{2}y^2+\frac{1}{2}x^2-\frac{1}{3}x^3$ 
- Critical points are $(0,0)$;$(1,0)$
- The Jacobian $J(x,y) = \begin{bmatrix} 0 & 1 \\ 2x-1 & 0\end{bmatrix}$
- At $(0,0)$ $\begin{bmatrix}0 & 1 \\ -1 & 0\end{bmatrix}$ eigenvalues are $\lambda=\pm i$ center
- At $(1,0)$ $\begin{bmatrix}0&1\\1&0\end{bmatrix}$ eigenvalues are $\lambda=\pm 1$ saddle $\vec{v_{+}} = <1,1>$, $\vec{v_{-}} = <1,-1>$