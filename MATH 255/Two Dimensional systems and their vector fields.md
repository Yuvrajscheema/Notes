- We consider the system $\vec{x} = P \vec{x}'$ with $\vec{x} = <x,y>$ where $P$ is a $2 \times 2$ matrix
- This system is autonomous and its solutions can be represented graphically by parameterized curves
- These solutions are called **trajectories** or **solution curves**
- The diagram of all trajectories is called the **phase portrait**
- At each point we can draw the direction vector $(\vec{x}',\vec{y}')$ - a solution is tangent to the direction field everywhere
- Example, draw the phase portrait of $x' = 2y -x$ and $y' = x$
![[IMG_9A0C46AFB354-1.jpeg]]
- There is one critical point solution of $\vec{x}' = 0$ namely $\vec{x} = 0$ corresponding to an equilibrium solution assuming $P$ is a non-singular matrix
- There are six possible cases depending on the eigenvalues of $P$
# Case 1: Distinct, real, positive eigenvalues
- Classification: unstable node, stability: unstable, nodal source
- The solution is expressed as $\vec{x}(t) = C_{1}\vec{v_{1}}e^{\lambda_{1}t}+C_{2}\vec{v_{2}}e^{\lambda_{2}t}$ $0 < \lambda_{1} < \lambda_{2}$
- $\lambda_{1}$ describes behaviour when $t$ is small
- If $C_{1}, C_{2} \neq 0$ then $||\vec{x}(t)|| \rightarrow \infty$ as $t \rightarrow \infty$ 
- Therefore all solutions different from $<0,0>$ grow, the critical point is unstable
- **Behaviour of $\vec{x}$** 
- As $t \rightarrow \infty$ $\vec{x_{1}} = C_{1}\vec{v_{1}}e^{\lambda_{1}t}$ and $\vec{x_{2}} = C_{1}\vec{v_{2}}e^{\lambda_{2}t}$ grow in magnitude but $\vec{x_{2}}$ grows faster
- As $t \rightarrow - \infty$ $\vec{x_{1}}$ will dominate
- Classify the c.p. $\vec{0}$ and its stability and sketch the associated phase portrait
- $\vec{x}' = \begin{bmatrix} 1 \quad 0 \\ 1 \quad 2\end{bmatrix}\vec{x}$ $\lambda_{1} = 1, \lambda_{2} = 2$ , $0 < 1 < 2$  $\vec{0}$ is a nodal source and is unstable
- To draw the phase portraits we must draw 
	- Eigendirections
	- Nullclines
	- Trajectories
- $(1)$ Eigendirections
	- Find eigenvectors,
	- $\vec{v_{1}} = <-1,1>$ corresponding to weak eigenvalue so weak ED
	- $\vec{v_{2}} = <0,1>$ strong ED
- $(2)$ Nullclines
	- rewrite the system as $\begin{cases} x' = f(x,y) \\ y' = g(x,y)\end{cases}$ 
	- The $x$ nullclines is the set of points in the plane verifying $f(x,y) = 0$ 
	- The $y$ nullclines is the set of points in the plane verifying $g(x,y) = 0$ 
	- The nullclines determine a change of sign/direction of the components of the vectors composing the direction field. We don't really need to draw directions for many points, we are interested in an overall description of the trajectories, that's how nullclines are helpful
	- Now back to the example
	- $f = x, g = x+2y$
	- $x$NC, $f = 0 \iff x = 0$
	![[IMG_54378CB676D9-1.jpeg]]
	- $y$NC $g = 0 \iff y = -\frac{x}{2}$
	![[IMG_F02D3094B113-1.jpeg]]
	- We have $(1)$ and $(2)$. We can now draw the phase portrait associated to the system and then draw $(3)$
	![[IMG_17D0C670159D-1.jpeg]]
	- Note 1: we draw the eigendirections and their associated line, For any point on these lines, we have $\vec{x} = \alpha \vec{v_{1}}$ or $\vec{v_{2}}$ Then $\vec{x}' = P \vec{x} = \lambda_{1}\alpha \vec{v_{1}}$ since $\lambda_{1} > 0$ if $\alpha>0$ then $\vec{x}$ points in the direction $\vec{v_{1}}$ and the opposite if $\alpha < 0$ 
	- Note 2: show the increasing time on the trajectories with an arrow 
# Case 2: distinct real, both negative
- Classification: nodal sink or stable node, stability: stable
- $\lambda_{1} < \lambda_{2} < 0$
- Look online for rest of notes, lecture 27-28
# Case 3: distinct real, opposite signs
- classification, saddle point, stability: unstable
- $\lambda_{1} < 0 < \lambda_{2}$
- Look online for rest of notes, lecture 27-28
# Case 4: purely imaginary eigenvalues
- $\lambda_{1,2} = \pm ib$
- Classification: center, stability: neutrally stable
- Look online for rest of notes, lecture 27-28
# Case 5: complex eigenvalues, Re($\lambda_{1},\lambda_{2}$) $>0$
- Classification: spiral source, stability: unstable
- $\lambda_{1,2} = a \pm ib$, $a > 0$
- Look online for rest of notes, lecture 27-28
# Case 6: complex eigenvalues, Re($\lambda_{1},\lambda_{2}$) $<0$
- Classification: spiral sink, stability: stable
- $\lambda_{1,2} = a \pm ib$, $a < 0$
- Look online for rest of notes, lecture 27-28
# Case 7: real, $\lambda_{1} = \lambda_{2}$
- $\lambda>0$: source
- $\lambda < 0$: sink