# Time independent non-homogeneous BC
## Dirichlet BC
- $u_{t}=\alpha^{2}_{x x}$
- $u(0,t)=u_{0}, \quad u(L,t)-u_{1}$
- $u(x,0)=f(x)$
- $u(x,t)=v(x,t)+\bar{u}(x,t)$
### Steady state problem
- Solution is independent of time
- $u_{t}=\alpha^{2}u_{x x}$
- $u(0,t)=u_{0}, \quad u(L,t)=u_{1}$
- $u(x,0)=f(x)$
- **Step 1** find the steady state solution
- $u_{t}=u_{xx} = 0\implies u_{\infty}(x)=Ax+B$, the solution in the long run
- $u_{\infty}(0)=B=u_{0}\quad u_{\infty}(L)=AL+u_{0}=u_{1}$
- $u_{\infty}(x)=\frac{{u_{1}-u_{0}}}{L}x+u_{0}$
- $u(x,t)=v(x,t)+u_{\infty}(x)$
- $u_{t}=v_{t}$
- $u_{xx}=v_{x x}+0 \implies v_{t}=v_{x x}\implies$PDE
### Boundary and initial conditions
- $u(0,t)=v(0,t)+u_{\infty}(0)$
- $u_{0}=v(0,t)+u_{0}\implies v(0,t)=0$
- $u(L,t)=v(L,t)+u_{\infty}(L)$
- $u_{1}=v(L,t)=u_{1}\implies v(L,t)=0$
- $u(x,0)=v(x,0)+u_{\infty}(x)$
- $v(x,0)=f(x)=u_{\infty}(x)$
### Solve the PDE
- As done in [[PDEs#Separation of Variables|separation of variables]]
- $v(x,t)=\sum_{n=1}^{\infty}b_{n}\sin\left( \frac{n\pi x}{L} \right)e^{-a^{2}(\frac{n\pi}{L})^{2}t}$
- $b_{n}=\frac{1}{L}\int_{-L}^{L}[f(x)-u_{\infty}(x)]\sin\left( \frac{n\pi x}{L} \right)$
- $u(x,t)=u_{\infty}(x)+v(x,t)$
# Types of Particular solutions
## Dirichlet
- $u_{\infty}(x)=Ax+B$
## Mixed type 1/2
- $u_{\infty}(x)+Ax+B$
## Neumann
- $u_{p}(x,t)=Ax^{2}+Bx+Ct$     particular solution
- $u_{t}=u_{x x}$
- $u_{x}(0,t)=q_{0},\quad u_{x}(L,t)=q_{1}$
- Assume we have a steady state problem
- $0=u_{x x}\implies u_{\infty}(x)=Ax+B$
- $u_{\infty}'(x)=A$
- $u_{\infty}'(0)=q_{0}=A$
- $u'_{\infty}(L)=q_{1}=A$
- This is only possible if $q_{0}=q_{1}=A$
- Since Neumann condition does not allow steady state unless $q_{0}=q_{1}$ let $u_{p}(x,t)=Ax^{2}+Bx+Ct$
- $\frac{ \partial u_{p} }{ \partial t }=c$
- $\frac{ \partial^{2}u_{p} }{ \partial x^{2} }=2A$
- So then we must have that $C=2A$
- $u_{px}(x,t)=2Ax+B$
- $u_{px}(0,t)=B=q_{0}$
- $u_{px}(L,t)=2AL+B=q_{1}\implies A=\frac{{q_{1}-q_{0}}}{2L}$
- So now we can write $u_{p}(x,t)=\frac{q_{1}-q_{0}}{2L}x^{2}+q_{0}x+\frac{q_{1}-q_{0}}{L}t$ 
# Eigen Function Expansion
- Given $u(x,t)=v(x,t)+u_{p}(x,t)$
- Let $v(x,t)=\sum_{n=0}^{\infty} V_{n}(t)b_{n}\sin\left( \frac{n\pi x}{L} \right)$
- $F(x,t)=\sum_{n=0}^{\infty}S_{n}(t)\sin\left( \frac{n\pi x}{L} \right)$ this is the source term
- Our aim is to  get the coefficients
- $v_{t}=\sum_{n=0}^{\infty}V_{n}'(t)\sin\left( \frac{n\pi x}{L} \right)$
- $v_{x x}=\sum_{n=0}^{\infty}-\left( \frac{n\pi}{L} \right)^{2}V_{n}(t)\sin\left( \frac{n\pi x}{L} \right)$
- Remember the solution is $v_{t}=v_{x x}+F(x,t)\implies v_{t}-v_{x x}-F(x,t)=0$
- So then we have the following
- $\sum_{n=0}^{\infty}\left[ V_{n}'+\left( \frac{n\pi}{L} \right)^{2}V_{n}-S_{n}(t) \right]\sin\left( \frac{n\pi x}{L} \right)=0$
- $S_{n}(t)$ is known
- $V_{n}'(t)+\left( \frac{n\pi}{L} \right)^{2}V_{n}(t)=S_{n}(t)$ which is a first order ode

# Examples
## Example 1
- $u_{t}=u_{xx}$
- $u_{x}(0,t)=\ln t \quad u_{x}(1,t)=t^{2}$
- $u(x,0)=f(x)$
- **Find a particular solution**
- $u_{p}(x,t)=\frac{A(t)}{2}x^{2}+B(t)x+C(t)t$
- $\frac{ \partial u_{p} }{ \partial x }=A(t)x+B(t)$
- $u_{x}(0,t)=\ln t=u_{px} =B(t)$
- $u_{x}(1,t)=t^{2}=A(t)+\ln t$
- $A(t)=t^{2}-\ln t$
- $u_{p}(x,t)=\frac{t^{2}-\ln t}{2}x^{2}+\ln (t) x$  we are ignoring $C(t)$ since this matches the boundary conditions
- $u(x,t)=v(x,t)=u_{p}(x,t)$
- $v_{t}+\frac{\left( 2t-\frac{1}{t} \right)}{2}c^{2}+\frac{x}{t}=v_{xx}+t^{2}-\ln t$
- $v_t=v_{xx} +t^{2}-\ln t-\frac{x}{t}-\frac{ 2t-\frac{1}{t} }{2}x^{2}$
- $v_{x}(0,t)=v_{x}(1,t)=0$
- $v(x,0)=f(x)-u_{\infty}(x,0)$
- This doesn't work for $\ln t$ lmao we need to change it to something like $\ln(t+1)$
## Example 2
- $u_{t}=16u_{xx}+\cos\left( \frac{7\pi x}{2} \right)\quad 0<x<2$
- $u_{x}(0,t)=1=u_{x}(2,t)$
- $u(x,0)=x^{2}-4$
- $u(x,t)=v(x,t)+u_{p}(x,t)$
- $u_{p}(x,t)=\frac{A(t)}{2}x^{2}+B(t)x+C(t)$
- $\frac{ \partial u_{p} }{ \partial x }=A(t)x+B(t)$
- $u_{p_{x}}(0,t)=B=1$
- $u_{p_{x}}(2,t)=1=2A+1\implies A=0$
- $u_{p}(x,t)=x$
-  $u(x,t)=v(x,t)+x$, now plug these into the pde
- $v_{t}=16v_{xx}+\cos\left( \frac{7\pi x}{2} \right)$
- $v_{x}(0,t)=v_{x}(2,t)=0$
- $u(x,0)=v(x,0)+u_{p}(x,0)\implies v(x,0)=x^{2}-4-x$
- Let $v(x,t)=\frac{V_{0}}{2}+\sum_{n=1}^{\infty}V_{n}\cos\left( \frac{n\pi x}{2} \right)$
- For a neumann $\lambda_{n}\in\begin{cases}0,\left( \frac{n\pi}{L} \right)^{2}\end{cases}$
- $\cos\left( \frac{7n\pi}{2} \right)=\frac{S_{0}}{2}+\sum S_{n}(t)\cos\left( \frac{n\pi x}{2} \right)$
- $S_{n}=\frac{2}{L}\int_{0}^{L}f(x)\cos\left( \frac{n\pi x}{2} \right)$
- $S_{n}=\delta_{n 7}$
- $v_{t}=\frac{V_{0}}{2}+\sum_{n=1}^{\infty}V_{n}'\cos\left( \frac{7\pi x}{2} \right)$
- $v_{xx}=\sum_{n=1}^{\infty}-\left( \frac{n\pi}{2} \right)^{2}V_{n}\cos\left( \frac{n\pi x}{2} \right)$
- $v_{t}-16v_{x x}-\cos\left( \frac{7\pi x}{2} \right)=0$
- $\left[ \frac{V_{t_{0}}}{2} -16[0]-0\right]+\sum_{n=1}^{\infty}\left[ V_{n}'+16\left( \frac{n\pi}{2} \right)^{2}V_{n}=\delta_{n_{7}} \right]\cos\left( \frac{n\pi x}{2} \right)$
- $\frac{\frac{ \partial V_{0} }{ \partial t }}{2}=0$ (1)
- $V_{n}+\left( \frac{4n\pi}{2} \right)^{2}V_{n}-\delta_{n_{7}}=0$ (2)
- From (1) we have that $V_{0}=C_{0}$
- From (2) we have $V_{x_{n}}+(2\pi n)^{2}V_{n}=\delta_{n_{7}}$
- Here we must use integrating factor, $r=e^{\int (2n\pi)^{2}dt}=e^{(2n\pi)^{2}t}$
- $V_{n}=e^{-(2n\pi)^{2}t}\left[ \int_{0}^{t}e^{(2n\pi)^{2}t}\delta_{n 7}dz+C \right]$
- $V_{n}=e^{-(2n\pi)^{2}t}\left[ \frac{1}{(2n\pi)^{2}}e^{(2n\pi)^{2}t}\delta_{n 7 }+C \right]$
- $V_{n}(t)=\frac{1}{(2n\pi)^{2}}S_{n 7}+Ce^{-(2n\pi)^{2}t}$
- $v(x,t)=\frac{c_{0}}{2}+\sum_{n=1}^{\infty} \left[ \frac{1}{(2n\pi)^{2}}\delta_{n 7}+C_{n}e^{-(2n\pi)^{2}t} \right]\cos\left( \frac{n\pi x}{2} \right)$
- $v(x,0)=\frac{c_{0}}{2}+\sum_{n=1}^{\infty}\left[ \frac{\delta_{n 7}}{(2n\pi)^{2}}+C_{n} \right]\cos\left( \frac{n\pi x}{2} \right)$
- $a_{n}=\frac{1}{L}\int_{-L}^{L}f(x)\cos\left( \frac{n\pi x}{L} \right)dx, \quad L=2$
- $c_{n}=a_{n}-\frac{\delta_{n 7}}{(2n\pi)^{2}}$
## Example 3
- $u_{t}=u_{x x}+e^{-t}\sin(x),\quad 0<x< \frac{\pi}{2}$
- $u_{0}(0,t)=0,\quad u_{x}\left( \frac{\pi}{2},t \right)=e^{-t}$
- $u(x,0)=x$
- We have mixed boundary conditions
- $\lambda_{n}-\mu_{n}^{2}\implies \mu_{n}=2n+1$
- $X_{n}(x)=\sin((2n+1)x)$
- $u_{p}(x,t)=A(t)x+B(t)$
- $u_{p}(0,t)=B(t)=0$
- $u_{p_{x}}(x,t)=A(t)\implies A(t)=e^{-t}$
- $v_{t}=e^{-t}x=v_{xx}+0+e^{-t}\sin(x)$
- $v(t)=v_{x x}+e^{-t}[x+\sin x]$
- $u(x,0)=v(x,0)+u_{p}(x,0)$
- $x=v(x,0)+x \implies v(x,0)=0$
- $v(x,t)=\sum_{n=0}^{\infty}V_{n}(t)+\sin((2n+1)x)$
- $e^{-t}[x+\sin x]=\sum_{n=0}^{\infty}S_{n}(t)\sin((2n+1)x)$
- So we know that $S_{n}(t)=\frac{2}{\frac{\pi}{2}}\int_{0}^{\pi/2}[x+\sin x]\sin((2n+1)x)dx$
- $\int_{0}^{\pi/2} x\sin[(2n+1)x] \, dx$
- $dv=\sin[(2n+1)x]$
- $v=-\frac{1}{2n+1}\cos[(2n+1)x]$
- $u=x,\quad du=1$
$\int_{0}^{\pi/2} x\sin[(2n+1)x] \, dx=-\frac{x}{2n+1}\cos((2n+1)x)\mid_{0}^\frac{\pi}{2}+\frac{1}{2n+1}+\frac{1}{2n+1}\int_{0}^{\pi/2}\cos((2n+1)x)  \, dx$
- This gives us $0+\frac{(-1)^{n}}{(2n+1)^{2}}+\frac{\pi}{4}$
- 
