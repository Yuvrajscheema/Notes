>[!Theorem]
>Let $\vec{x}' = P \vec{x} + \vec{f}$ be a linear system of ODEs. Suppose $\vec{x_{p}}$ is a particular solution. 
>Then every solution can be written as $\vec{x} = \vec{x_{c}}+\vec{x_{p}}$ where $\vec{x_{c}}$ is the complementary solution

# Variation of parameters
- Consider $x' = Px + f$ ($\star$)
- Assume we have $x_{c}$ and obtained a fundamental matrix solution $X(t) = \big( x_{1} +\dots + x_{n}\big)$
- The general solution of the homogeneous system is $X(t)\vec{c}, \vec{c} = (c_{1, \dots{} } c_{n})$
- We assume that $x_{p} = X(t)\vec{u}$
- Plugging into ($\star$) gives us $x_{p}' = Px_{p}+f \implies X \vec{u}'+ X' \vec{u} = PX \vec{u}+f$
- Note, we know that $X' = PX$ since every column of $X$ verifies $x' = Px$
- The previous relation becomes $X \vec{u}' = f \implies \vec{u}' = X^{-1}f$
- After integrating we get $\vec{u} = \int X^{-1}f \, dt$
- And finally $x_{p} = Xu = X\int X^{-1}f \, dt$
>[!Example]
>Solve $x' = \begin{bmatrix} -2 & 1 \\ 1 & -2\end{bmatrix}x + \begin{bmatrix} 2e^{-t} \\ 3t \end{bmatrix}$
>$x_{c} = C_{1}\begin{bmatrix} 1 \\ 1\end{bmatrix}e^{-3t} + C_{2} \begin{bmatrix} 1 \\ 1\end{bmatrix}e^{-1}$
>$X = (x_{1} + x_{2})$ this is a fundamental matrix
>$X = \begin{bmatrix} e^{-3t}& e^{-t} \\ -e^{-3t}& e^{-t}\end{bmatrix}$
> Note, the formula for the inverse of a $2 \times 2$ matrix is $A^{-1} = \frac{1}{\det{A}} \begin{bmatrix} d & -b \\ -c & a \end{bmatrix}$
> $\det(X) = 2e^{-4t}$
> $X^{-1}= \frac{1}{2e^{-4t}} \begin{bmatrix} e^{-t} & -e^{-t}\\ e^{-3t}& e^{-3t} \end{bmatrix} = \frac{1}{2}\begin{bmatrix} e^{3t}&-e^{3t} \\ e^{t}&e^t \end{bmatrix}$
> $x^{-1}f = \frac{1}{2}\begin{bmatrix} e^{3t}&-e^{3t} \\ e^{t}&e^{t} \end{bmatrix} = \begin{bmatrix} e^{2t}&-\frac{3}{2}te^{3t} \\ 1& \frac{3}{2}te^{t} \end{bmatrix}$
> Now lets solve $\vec{u}$
> $u_{1} = \int e^{2t-\frac{3}{2}te^{3t}\,dt}\Rightarrow u_{1} = \frac{e^{2t}}{2}-\frac{te^{3t}}{2}+\frac{1}{6}e^{3t}+K_{1}$
> $u_{2} = \int_{1}+\frac{3}{2}te^{t\,dt}\Rightarrow u_{2} =t+\frac{3}{2}te^{t}-\frac{3}{2}e^t+K_{2}$
> Choose $K_{1} = K_{2} = 0$
> Now finally $x_{p} = Xu$
> $x_{p} = \begin{bmatrix} e^{-3t}& e^{-t} \\ -e^{-3t}& e^{-t}\end{bmatrix} \begin{bmatrix}\frac{e^{2t}}{2}-\frac{te^{3t}}{2}+\frac{1}{6}e^{3t} \\   t+\frac{3}{2}te^{t}-\frac{3}{2}e^t\end{bmatrix}$
> After some matrix multiplication and simplification we get,
> $x_{p} = e^{-t}\begin{bmatrix} \frac{1}{2} \\ -\frac{1}{2} \end{bmatrix} + te^{-t} \begin{bmatrix} 1 \\ 1 \end{bmatrix} + t \begin{bmatrix} 1 \\ 2\end{bmatrix} - \begin{bmatrix} \frac{4}{3} \\ \frac{5}{3} \end{bmatrix}$











