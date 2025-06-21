- When you solve the [[PDEs#Heat equation with Dirichlet B.C. (Sine series)|heat equation]] you get a function $f(x)=\frac{a_{0}}{2}+\sum_{n=1}^{\infty}a_{n}\cos\left( \frac{n\pi x}{L} \right)+b_{n}\sin\left( \frac{n\pi x}{L} \right)$ which is a Fourier series
>[!Definition]
>A function is **piecewise continuous** in the interval $[a,b]$ if it has a finite number of discontinuities in $[a,b]$ and has finite left and right limit at the points of discontinuity

- Fourier series applies to the periodic extension of $f(x)$, denoted $f_{\text{per}}(x)$
- **1** Even extension, Neumann Boundary condition we mirror what happens from $0 \to L$ is mirrored across the axes to $0\to-L$
- **2** Odd extension , Dirichlet Boundary Condition, what happens from $0\to L$ would be flipped from $0\to-L$
- **3** Periodic Extension, periodic boundary conditions, what happens from $0\to L$ is the same as what happens from $-L\to 0$
- **Convergence**  if $f(x)=\frac{a_{0}}{2}+\sum_{n=1}^{\infty}a_{n}\cos\left( \frac{n\pi x}{L} \right)+b_{n}\sin\left( \frac{n\pi x}{L} \right)$ Fourier series converges to $f(x)$ at all $x$ where $f(x)$ is continuous and to $\frac{1}{2}[f(x^{+}+f(x^{-}))]$
- At the point of discontinuity the Fourier series struggles and oscillates, this is called the **Gibbs phenomenon**
- 