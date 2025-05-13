- Questions on the "things to integrate" line:    **PDEs**
	1.  We know curl(grad$f$) $= \vec{0}$ but if curl$\vec{F} = 0$ does there exist $f$ such that $\vec{\nabla}f = \vec{F}$ 
	2. We know div(curl$\vec{G}$) $=\vec{0}$ but if div$\vec{F}=\vec{0}$ does there exist $\vec{G}$ such that $\vec{\nabla}\times \vec{G}=\vec{F}$ 
- Answers to 1 and 2 are equivalent to the answers to the analogous questions 1 and 2
- Questions on the "places to integrate" line:            **Topology**
	1. We know that $\partial(\partial S)=\varnothing$ but if $\partial C=\varnothing$ does there exist $S$ with $\partial S=C$?
	2. We know that $\partial(\partial E)=\varnothing$ but if $\partial S=\varnothing$ does there exist $E$ with $\partial E=S$?
- All of this begs the question: is there some unifying principal? YES!! TO see it requires us to translate this all into a different and better language. **Differential Forms**
# Differential Forms
- Let $x_{i},\dots x_{n}$ be coordinate on $\mathbb{R}^n$. Introduce symbols $dx_{1},\dots,dx_{n}$ and the "wedge product" a satisfying the one rule $dx_{i}\wedge dx_{j}=-dx_{j}\wedge dx_{i}$. Let $U \subset\mathbb{R}^n$ be an open set
- A differential k-form on $U$ is a formal linear combination of k-fold wedge products of the $dx_{i}$'s where the coefficients are functions on $U$
- For example let $U\subset\mathbb{R}^3$ and let $x,y,z$ be the usual coordinates on $\mathbb{R^3}$. Then for example 1-forms are given by expressions of the form $Pdx+Qdy+Rdz$ where $P,Q,R$ are functions on $U$.
- Since our rules tell us $dx\wedge dy=-dy \wedge dx$, etc we find all 2-forms can be written in the form $Pdy\wedge dz+Qdz\wedge dx+Rdx\wedge dy$ note the rule forces $dx\wedge dx=0,dy\wedge dy=0,\dots$
- Similarly, since $dx\wedge dy\wedge dz=-dx\wedge dz\wedge dy=dz\wedge dx\wedge \wedge dy$ etc... all 3-forms can be written as $f(x,y,z)dx\wedge dy\wedge dz$. $f$ is a function on $U$. There can't be any k-forms for $k\geq4$ and 0-forms are just functions. We denote the set of k-forms on $U$ by $\Omega^{k}(u)$ 
	- $f(x,y,z)\quad$$\Omega^{0}\longleftrightarrow$ functions $f$
	- $Pdx+Qdy+Rdz \quad$ $\Omega^{1}(u)\longleftrightarrow$ vector fields $<P,Q,R>$
	- $Pdy\wedge dz+Qdz\wedge dz+Rdx\wedge dy \quad$ $\Omega^{2}(u)\longleftrightarrow$ Vector fields $<P,Q,R>$
	- $fdx\wedge dy\wedge dz \quad$ $\Omega^{3}(u)\longleftrightarrow$ functions $f$
- Wedge product extends to forms $\wedge:\Omega^{k}(u)\times \Omega^{l}(u)\longrightarrow\Omega^{k+l}$ you just multiply, expand, then apply the rule
>[!Example]
>$(F_{1}dx+F_{2}dy+F_{3}dz)\wedge(G_{1}dx+G_{2}dy+G_{3}dz)$
>$=F_{1}G_{1}dx\wedge dx+F_{1}G_{2}dx\wedge dy+F_{1}G_{3}dx\wedge dz$
>$+F_{2}G_{1}dy\wedge dx+F_{2}G_{2}dy\wedge dy+F_{2}G_{3}dy\wedge dz$
>$+F_{3}G_{1}dz\wedge dx+F_{3}G_{2}dz\wedge dy+F_{3}G_{3}dz\wedge dz$
>$=(F_{2}G_{3}-F_{3}G_{2})dy\wedge dz+(F_{3}G_{1}-F_{1}G_{3})dz\wedge dx+(F_{1}G_{2}-F_{2}G_{1})dx\wedge dy\longleftrightarrow$ $<F_{1},F_{2},F_{3}>\times<G_{1},G_{2},G_{3}>$
- So $\wedge: \Omega^{1}(u)\times \Omega^{1}(u)\rightarrow \Omega^{2}(u)$ corresponds to the cross-product of vector fields under our dictionary
>[!Example]
>$(F_{1}dx+F_{2}dy+F_{3}dz)\wedge(G_{1}dy\wedge dz+G_{2}dz\wedge dx+G_{3}dx\wedge dz)$
>$=\dots$
>$=(F_{1}G_{1}+F_{2}G_{2}+F_{3}G_{3})dx\wedge dy\wedge dz$
- So $\wedge:\Omega^{1}(u)\times \Omega^{2}(u)\longrightarrow\Omega^{3}(u)$ corresponds to dot product of vector fields under our dictionary
- In general, if $w\in \Omega^{k}(u)$ and $n\in \Omega^{l}(u)$ $w\wedge n=(-1)^kn\wedge w$
# The One Derivative to Rule Them All
- We now define the **One Derivative to Rule Them All**:$d:\Omega^{k}(u)\rightarrow \Omega ^{k+1}(u)$ for $k=0$ we define $df=\frac{\partial f}{\partial x}dx+\frac{\partial f}{\partial y}dy+\frac{\partial f}{\partial z}dz$ for all other $k$, apply d to each coefficient and then use wedge product to expand
>[!Example]
>$w=Pdx+Qdy+Rdz$ then $dw=dP\wedge dx+dQ\wedge dy+dR\wedge dz$
>$=(P_{x}dx+P_{y}dy+P_{z}dz)\wedge dx$
>$+(Q_{x}dx+Q_{y}dy+Q_{z}dz)\wedge dy$
>$+(R_{x}dx+R_{y}dy+R_{z}dz)\wedge dz$
>$=(R_{y}-Q_{z})dy\wedge dz+(P_{z}-R_{x})dz\wedge dx+(Q_{x}-P_{y})dx\wedge dy$
- So $d:\Omega^{1}(u)\rightarrow \Omega^{2}(u)$ corresponds to curl under our dictionary
- Similarly $d(Pdy\wedge dz+Qdz\wedge dx+Rdx\wedge dy)=(P_{x}+Q_{y}+R_{z})dx\wedge dy\wedge dz$ so $d:\Omega^{2}(u)\longrightarrow\Omega^{3}(u)$ corresponds to div under our dictionary
- $\Omega^{0} \quad \longrightarrow\ \quad \Omega^{1}(u) \quad\longrightarrow \quad \Omega^{2}(u) \quad\longrightarrow\Omega^3(u)$
- functions $\longrightarrow$(grad) vector fields $\longrightarrow$(curl) vector fields $\longrightarrow$(div) functions
- In general we have $d^{2}=0$ 
- We also have $\alpha\in \Omega^{k}(u)$ then $d(\alpha \wedge \beta)=(d \alpha)\wedge \beta+(-1)^{k}\alpha \wedge d\beta$ 
>[!Example]
>$\alpha$ is a 0-form, $f$ is a function
>$\beta$ is a 1-form, $\vec{F}$ is a vector field
>$d(\alpha \wedge \beta)$,(curl($f\vec{F}$)) = $d\alpha \wedge \beta$($\vec{\nabla}f\times \vec{F}$) + $\alpha \wedge d\beta$($f$curl$\vec{F}$)

>[!Example]
>$\alpha$ is a 1-form, $\vec{F}$ is a function
>$\beta$ is a 1-form, $\vec{G}$ is a vector field
>$d(\alpha \wedge \beta)$,(div($\vec{F}\times \vec{G}$)) = $d\alpha \wedge \beta$(curl$\vec{F}\cdot \vec{G}$) - $\alpha \wedge d\beta$($\vec{F}\cdot \text{curl}\vec{G}$)

# Excursion into $\mathbb{R}^4$. Maxwell's equations
- $\vec{B}= <B_{1},B_{2},B_{3}>$ magnetic field
- $\vec{E}= <E_{1},E_{2}E_{3}>$ electric field
- $\vec{J}= <j_{1},j_{2},j_{3}>$ current density
- $\rho$
- $\vec{\nabla}\cdot \vec{B}=0\quad\quad \vec{\nabla}\cdot \vec{E}=\frac{\rho}{\varepsilon_{0}}\quad\quad \vec{\nabla}\times \vec{E}+\frac{\partial \vec{B}}{\partial t}=\vec{0}\quad\quad\vec{\nabla}\times \vec{B}-\frac{1}{c^{2}} \frac{\partial \vec{E}}{\partial t}=\mu_{0}\vec{J}$
- $\varepsilon_{0},\mu_{0},c$ are electric constant, magnetic constant, speed of light, we can use units where these are all 1
- This formulation makes it look like $\vec{E}$ and $\vec{B}$ are 2 different things, but under a Lorentz transformation, $\vec{E}$ and $\vec{B}$ get scrambled. They are really two components of a single two form
- $\mathbb{R}^4$ has coordinates $x,y,z,t$ the electromagnetic 2-form $F$ is given by $F=B_{1}dy\wedge dz+B_{2}dz\wedge dx+B_{3}dx\wedge dy+(E_{1}dx+E_{2}dy+E_{3}dz)\wedge dt$
- $J=\rho dx\wedge dy\wedge dz-(j_{1}dy\wedge dz+j_{2}dz\wedge dx+j_{3}dx\wedge dy)\wedge dt$ current 3-form
- $F\in \Omega^{2}(\mathbb{R^4})$ $J\in \Omega^{3}(\mathbb{R}^4)$ 
- **Hodge star operator** $\star:\Omega^{2}(\mathbb{R}^4)\longrightarrow\Omega^{2}(\mathbb{R}^4)$
	- For any coordinate 2-form $\alpha$, define $\star \alpha$ to be the coordinate 2-form such that $\alpha \wedge \star \alpha=dt\wedge dx\wedge dy\wedge dz$ 
	- $\star(dx\wedge dy)=dt\wedge dz$
	- $\star(dy\wedge dz)=dt\wedge dx$
	- $\star(dz\wedge dx)=dt\wedge dy$
	- $\star(dx\wedge dt)=dy\wedge dz$
	- $\star(dy\wedge dt)=dz\wedge dx$
	- $\star(dz\wedge dt)=dx\wedge dy$
	- $\circ\wedge\circ$
- Maxwell's equations: $dF=0\quad\quad d(\star F)=J$
- Note: if the domain is $\mathbb{R}^4$, then $dF=0\Rightarrow \exists A\in \Omega^{1}(\mathbb{R^4})$ such that $F=dA$. A is called the electromagnetic gauge field. It is the fundamental object. It is a 1-form, unique up to a gauge transformation $A\longmapsto A+df$ where $f$ is a function
- Note $d^{2}=0\Rightarrow dJ=0$ the so called continuity equation
- The above description allows for a coordinate free description. Very important in understanding the symmetries of the equations.
# Integration, change of variables, (orientation)
- A k-form can be integrated on a k-dimensional (oriented) manifold
- We've already seen the integral of a 1-form over a 1-manifold C
- (i.e. a curve): $\int_{C}Pdx+Qdy+Rdz$ this was one of our ways of writing a work integral
- Also the integral of a 3-form $fdx\wedge dy\wedge dz$ over a 3-manifold E (a.k.a a solid) is just the usual triple integral $\int \int \int_{E} fdxdydz$ 
- A 0-manifold is a collection of points $p_{1},\dots,p_{k}$ (orientation associates a sign to each point)
- The integral of a 0-form $f$ over $\{ p_{1},\dots,p_{k} \}$ is a (signal) sum: $\sum_{i=1}^{k}\pm f(p_{i})$ 
- Consider a surface S and a 2-form $w=Pdy\wedge dz+Qdz\wedge dx+Rdx\wedge dy$. To define the integral $\int \int_{S}w$, we use the chain rule to write the 2-form in terms of the variables in a parameterization of S
- Let $\vec{r}(u,v)= <x(u,v),y(u,v),z(u,v)>$ $(u,v)\in D \subset \mathbb{R^2}$ then $dx=\frac{\partial x}{\partial u}du+\frac{{\partial x}}{\partial v}dv$, $dy=\frac{{\partial y}}{\partial u}du+\frac{{\partial y}}{\partial v}dv$, $dz=\frac{{\partial z}}{\partial u}du+\frac{{\partial z}}{\partial v}dv$ so:
- $dy\wedge dz=(y_{u}du+y_{v}dv)\wedge(z_{u}du+z_{v}dv)=(y_{u}z_{v}-y_{v}z_{u})du\wedge dv$
- $dz\wedge dx=(z_{u}x_{v}-z_{v}x_{u})du\wedge dv$
- $dx\wedge dy=(x_{u}y_{v}-x_{v}y_{u})du\wedge dv$
- and so $Pdy\wedge dz+Qdz\wedge dx+Rdx\wedge dy=\{ P(y_{u}z_{v}-y_{v}z_{u})+Q(z_{u}x_{v}-z_{v}x_{u})+R(x_{u}y_{v}-x_{v}y_{u}) \}du\wedge dv=$ $<P,Q,R>\cdot(\vec{r_{u}}\times \vec{r_{v}})$ 
- Thus $\int \int_{S}Pdy\wedge dz+Qdz\wedge dx+Rdx\wedge dy=\int \int_{D}<P,Q,R>\cdot(\vec{r_{u}} \times \vec{r_{v}})dudv$ which was exactly our notion of flux
- The way we just defined integration of 2-forms over surfaces basically works in general: we can define integration of n-forms over n-manifolds in the same way.
- **Generalized Stoke's Theorem**: Suppose $w\in \Omega^{k-1}(u)$ and $M$ is a k-manifold then $\int_{M}dw=\int_{\partial M}w$
	-  $\Omega^{0} \quad \longrightarrow\ \quad \Omega^{1}(u) \quad\longrightarrow \quad \Omega^{2}(u) \quad\longrightarrow\Omega^3(u)$
	- functions $\longrightarrow$(grad) vector fields $\longrightarrow$(curl) vector fields $\longrightarrow$(div) functions
	- points $\longleftarrow$ curves $\longleftarrow$ surfaces $\longleftarrow$ solids
	- $\mid$Sums (FTLI)$\mid$ line integrals (Stoke's theorem)$\mid$ flux integrals (divergence theorem) $\mid$ triple integrals
- A differential form $w\in \Omega^{k}(u)$ is called closed if $dw=0$. It is called exact if there is some $\alpha\in \Omega^{k-1}(u)$ such that $w=d\alpha$
- What are all the closed k-forms? In other words , what are all the solutions the equation $dw=0$ (really a system of PDEs). There are of course the "trivial" solutions: pick any $k-1$ from $\alpha$ and let $w=d\alpha$. The non-trivial solutions are given by closed $k$-form which are not exact. (For $k=1$ this is equivalent to asking for a vector field $\vec{F}$ such that curl$\vec{F}=\vec{0}$ but $\vec{F}$ is not conservative)
- The $k$-th DeRham cohomology can be thought of the space of solutions to PDE $dw=0$ modulo the space of trivial solutions: $H_{DR}^{k}(u)=\frac{\{ \text{closed } k\text{-froms}\}}{\{\text{exact }k\text{-forms}\}}$
- A $k$-manifold $M$ in $U$ is closed if $\partial M=\varnothing$. A closed $k$-manifold $M$ is called a boundary if there is a ($k+1$)-manifold E such that $\partial E=M$. the $k\text{-th}$ homology of $U$ is $H_{k}(u)=\frac{\{ \text{closed }k\text{-manifolds in U} \}}{\{\text{boundaries}\}}$ To fully make sense of this quotient, we need to make these sets into vector spaces: we do this by taking formal sums of manifolds
- For example $H_{1}(u)=0$ if every loop bounds a disk. If $H_{1}(u)\neq 0$ then $U$ is not simply connected
- The Derham theorem: $H_{DR}^{k}(u)\cong H_{k}(u)$ Integration is the connection between forms ($H_{DR}^k$) and manifolds ($H_{k}$) Stoke's theorem makes this work