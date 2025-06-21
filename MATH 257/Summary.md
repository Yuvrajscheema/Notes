# ODE Review
### Separation of Variables
### Linear First Order ODE
### Constant Coefficients 2nd Order
### Cauchy-Euler ODE
### Power Series Method
### Singular Points
- Classification of Singular Points
-  Frobenius method for RSP
-  Bessel Equation
# PDES
### Heat Equation
-  Finite Difference Method
	- Discretizing
	- Difference Schemes
- Boundary conditions
	- Dirichlet
		- $\lambda_{n}=-\left( \frac{n\pi}{L} \right)^{2},\quad \phi_{n}=\sin\left( \frac{n\pi x}{L} \right)$
	- Neumann
		- $\lambda_{n}=-\left( \frac{n\pi}{L} \right)^{2},\quad \phi_{n}=\cos\left( \frac{n\pi x}{L} \right)$
	- Periodic
		- $\lambda_{n}=-\left( \frac{n\pi}{L} \right)^{2},\quad \phi_{n}\begin{cases}\cos\left( \frac{n\pi x}{L}\ \right)\\sin\left( \frac{n\pi x}{L} \right) & \end{cases}$
	- Mixed Type A
		- $\lambda_{n}=-\left( \frac{(2n+1)\pi}{2L} \right)^{2},\quad \phi_{n}=\sin\left( \frac{(2n+1)\pi x}{2L} \right)$
	- Mixed Type B
		- $\lambda_{n}=-\left( \frac{(2n+1)\pi}{2L} \right)^{2},\quad \phi_{n}=\cos\left( \frac{(2n+1)\pi x}{2L} \right)$
- Separation of Variables
	- Fourier Series
	- Orthogonality
	- Heat Equation in a ring
	- Non homogeneous equations
		- Particular solutions
		- Steady state problems
### Wave Equation
-  Finite Difference Method
	- Discretizing
	- Difference Schemes
- Boundary conditions
	- Same as heat equation
- Separation of Variables
	- Fourier Series
	- Orthogonality
	- Heat Equation in a ring
	- Non homogeneous equations
		- Particular solutions
		- Steady state problems
- d'Almberts Solution
### Laplace Equation
-  Finite Difference Method
	- Discretizing
	- Difference Schemes
	- Jacobian Iteration Scheme
- Boundary conditions
	- Same as heat equation
- Domains
	- Rectangular domain
	- Disk
	- Semi Infinite Strip
- Separation of Variables
	- Fourier Series
	- Orthogonality
	- Heat Equation in a ring
	- Non homogeneous equations
		- Particular solutions
		- Steady state problems
# Sturm-Liouville
- $\mathcal{L}y=-\frac{d}{dx}\left( p(x)\frac{ d y }{ d x } \right)+q(x)y(x)$, the SL form
- Periodic boundary conditions are not SL problems
- Regular SL problems
	- Eigenvalues
	- Eigenfunctions
- Lagrange's Identity
- Robin Type Boundaries for Heat Equation