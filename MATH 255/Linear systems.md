# Complex eigenvalues
>[! Theorem]
>If $P$ is a real valued constant square matrix and it has complex eigenvalues
>$\lambda = a+ib$ with an associated eigenvector $\vec{v}$, then $\overline{\lambda} = a -ib$ is the complex conjugate eigenvalue with a complex conjugate eigenvector $\overline{\vec{v}}$

- Proof is in the online notes
>[! Example]
>Transform the IVP $\begin{cases} y''+2y'+2y=0 \\ y(0) = 0, y'(0) = 1 \end{cases}$ into a system of ODEs and solve
>Let $x_{1} = y, x_{2} = y'$ $\begin{cases} x_{1}' = y' \\ x_{2}' = y''\end{cases}$
>$\begin{cases} y'' = -2y' -2y = x_{2}' \\ x_{2}' = -2x_{2} -2x_{1} \end{cases}$
>so $x_{1}' = x_{2}$ and $x_{2}' = -2x_{2} - 2x_{1}$
>$\vec{x}' = \begin{bmatrix} 0 \quad 1 \\ -2 -2\end{bmatrix} \vec{x}(0) =\begin{bmatrix} 0 \\ 1\end{bmatrix}$
>The eigenvalues of $P$ are $\lambda = -1 \pm i$
>In the complex case we only need $\vec{v_{1}}$ which we will find using $\lambda_{1} = -1+i$
>This gives the eigenvector $\vec{v_{1}} = <1, -1+i>$
>Now we can apply the theorem
>$\vec{v_{1}}e^{\lambda_{1}t} = \begin{bmatrix} 1 \\ -1 + i \end{bmatrix} e^{(-1+i)t} = \begin{bmatrix} \cos{t} + i\sin{t} \\ (-1+i)(\cos t + i\sin t) \end{bmatrix}e^{-t}$
>This gives us
>$\vec{x}(t) = C_{1}e^{-t}\begin{bmatrix}\cos t\\ -\cos t-\sin t \end{bmatrix} + C_{2}e^{-t}\begin{bmatrix}\sin t\\ \cos t-\sin t \end{bmatrix}$
>Now we can solve the initial condition which finally gives us
>$\vec{x}(t) = e^{-t}\begin{bmatrix} \sin t \\ \cos t - \sin t\end{bmatrix}$
>$y = x_{1} = e^{-t}\sin t$

# Multiple Eigenvalues
- We still consider the $x' = Px$
- We covered the case where the eigenvalues are distinct, what happens if they are repeated
## Geometric and Algebraic Multiplicity
>[!Definition]
>The multiplicity of an eigenvalue $\lambda_{j}$ as a root of the characteristic polynomial is called the algebraic multiplicity e.g. $(\lambda -1)^{1}=0$, multiplicity of two
>The geometric multiplicity of and eigenvalue is the number of linearly independent eigenvectors associated to the eigenvalue

- Geometric multiplicity will always be less than or equal to algebraic
- Let $P = \begin{bmatrix}3 \quad_{} 0 \\ 0 \quad 3\end{bmatrix}$
- The eigenvalue $3$ has an algebraic multiplicity of two and now we can choose two linearly independent vectors in this set of vectors
- We have $\vec{v_{1} = <0,1>, \vec{v_{2}} = <1,0>}$
- So the algebraic multiplicity is two and the geometric multiplicity is two
>[!Theorem]
>If for each repeated eigenvalue of $P$ the AM equals the GM then the general solution is similar to the distinct real eigenvalues case
- The solution to the problem above would be $\vec{x}(t) = C_{1}\vec{v_{1}}e^{3t} + C_{2}\vec{v_{2}}e^3t$
## Defective eigenvalues
>[!Definition]
>If the GM is less than the AM then $\lambda_{j}$ is called **defective** and the difference AM - GM is the defect

- We can't apply the eigenvalue method to get the general solution
- Let $P = \begin{bmatrix} -2 \quad 1 \\ -1 \quad 0 \end{bmatrix}$
- $\lambda = -1$ has an algebraic multiplicity of two
- However all the eigenvectors will have the form $\vec{v} = <\alpha, \alpha>$ where $\alpha$ is a constant
- It is impossible to get two linearly independent vectors
- Why can't we apply the eigenvalue theorem? real case
	Because we need to have $n$ linearly independent vectors for an $n \times n$ matrix. Otherwise, for example, if we write the solution in a case where GM $<$ AM for a $2 \times 2$ system $\vec{x}(t) = C_{1}\vec{v_{1}}e^{\lambda t} + C_{2}\vec{v_{2}}e^{\lambda t} = (C_{1} + C_{2}R)\vec{v_{1}}e^{\lambda t}$ we are left with one solution to work with while we are looking for two linearly independent solutions to build the general solution
### We need to build an additional solution
- We already have one solution $\begin{cases} \vec{x_{1}} = \vec{v_{1}}e^{\lambda_{1} t} \\ (P - \lambda_{1}I)\vec{v_{1}} = 0\end{cases}$
- We guess $\vec{x_{2}} = (t\vec{v_{1}}+\vec{v_{2}})e^{\lambda_{2}t}$ 
- $(1)$ $Px_{2} = \vec{P}v_{1}te^{\lambda_{2}t} + P \vec{v_{2}}e^{\lambda_{2}t} = \lambda_{1}\vec{v_{1}}te^{\lambda_{1}t} + P \vec{v_{2}}e^{\lambda_{2}t}$
- $(2)$ $x_{2}' = \vec{v_{1}}e^{\lambda_{2}t} + t\lambda_{2}\vec{v_{1}e^{\lambda_{2}t}} + \vec{v_{2}}\lambda_{2}e^{\lambda_{2}t}$
- $(1) = (2) \implies \vec{v_{1}}e^{\lambda_{2}t} = (P - \lambda_{2}I)\vec{v_{2}}e^{\lambda_{2}t}$
- So $\vec{x_{2}}$ is a solution of $(P - \lambda_{2}I)\vec{v_{2}} = \vec{v_{1}}$. Also $\vec{v_{2}}$ is called a generalized eigenvector. Furthermore we have $(P - \lambda_{2}I)(P - \lambda_{2}I)\vec{v_{2}} = \vec{0} = (P - \lambda_{2}I)\vec{v_{1}}$  using $(P - \lambda_{1}I)\vec{v_{1}} = 0$ and the pervious relation. So we can get $\vec{v_{2}}$ solving $(P - \lambda_{2}I)^{2}\vec{v_{2}}= 0$ with $(P - \lambda_{2}I)\vec{v_{2}} \neq 0$ because $\vec{v_{1}}$ is an eigenvector
- And finally $\vec{v_{1}} = (P-\lambda_{2}I)\vec{v_{2}}$
### Now we can return to previous example
- We take $\vec{v_{1}} = <1,1>$, $x_{1} = <1,1>e^{-t}$
- Now lets find $x_{2}$. It is a solution if $(P+I)\vec{v_{2}} = \vec{v_{1}}$
- $\begin{bmatrix} -1 \quad 1 \\ -1 \quad 1 \end{bmatrix} \begin{bmatrix} v_{21} \\ v_{22}\end{bmatrix} = \begin{bmatrix} 1 \\ 1 \end{bmatrix}$
- $\vec{v_{2}} = <0,1>$ works!
- The general solution is $\vec{x}(t) = C_{1}\vec{x_{1}}(t) + C_{2}\vec{x_{2}}(t)$ with $\vec{x_{1}} = \begin{bmatrix} 1 \\ 1 \end{bmatrix}e^{-t}$ and $\vec{x_{2}} = \begin{bmatrix} t\begin{bmatrix} 1 \\ t \end{bmatrix} + \begin{bmatrix}  0 \\ 1\end{bmatrix}\end{bmatrix}e^{-t}$
- Another example is in the notes lecture 25-26 W9 2021