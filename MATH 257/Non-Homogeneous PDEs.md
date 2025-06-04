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
- 