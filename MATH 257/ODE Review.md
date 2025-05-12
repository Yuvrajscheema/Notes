# Separation of variables
- Any equation written as $y'=f(x,y,y',\dots,y^n)$ is a differential equation, this of first order if $n=1$
- The equation is linear if $f(x)$ is a linear function in $y$
- $\frac{ d y }{ d x }=f(x)g(y)$ is a separable equation, got to $\frac{dy}{g(y)}=f(x)dx$ and then integrate
>[!Example]
>$\frac{ d y }{ d x }=\frac{x+2}{y-3}$ so then $f(x)=x+2$ and $g(y)=y-3$
>We get the following $\frac{dy}{y-3}=(x+2)dx$ and then integrate
>$\frac{y^2}{2}=3y=\frac{x^2}{2}+2x+C$

# Linear First order ODE
- Equations of the form $y'=P(x)y=Q(x)$ or $ay'+by=c$ where $a,b,c$ are functions of $x$
- We use the integrating factor here, $\mu(x)=e^{\int P(x)dx}$
- With this integrating factor we write $\mu y'+\mu P(x)y=\mu Q(x)\implies(\mu y)'=\int \mu Q(x)dx+C$
- $y(x)=e^{-\int P(x)dx}\int e^{\int P(x)dx}Q(x)dx+C$
>[!example]
>$xy'+y=2x^{3}$
>$y'+\frac{1}{x}y=2x^2\implies P(x)=\frac{1}{x}$ so then $\mu=e^{\int \frac{1}{x}dx}=x$
>Now we have $\int (xy)'=\int 2x^3\,dx+C$
>Simplifying this gives $y=\frac{x^3}{2}+\frac{C}{x}$


# Second Order ODE
## Constant coefficients
- $ay''+by'+cy=d=0 \quad a,b,c,d \in \mathbb{R}$
- $y(x,r)=e^{rx}$
- $ar^{2}e^{rx}+bre^{rx}+ce^{rx}=0\implies ar^{2}+br+c=0$
- $r=\frac{{-b \pm \sqrt{ b^2-4ac }}}{2a}$ the stuff under the root is the discriminant
- **$b^2-4ac>0\implies$ two real distinct roots $r_{1},r_{2}$
- $y(x)=C_{1}e^{r_{1}x}+C_{2}e^{r_{2}x}$
- **$b^2-4ac=0\implies$ repeated roots, $r=-\frac{b}{2a}$
- We know $y_{1}(x)=C_{1}e^{rx}$, and $y_{2}=xe^{rx}$
- So $y(x)=C_{1}e^{rx}+C_{2}xe^{rx}$
- **$b^2-4ac<0\implies$ you get complex conjugate roots $r_{1}=\alpha+\beta i, r_{2}=\alpha-\beta i$
- $y(x)=C_{1}e^{(\alpha+\beta i)}+C_{2}e^{(\alpha-\beta i)}=e^{\alpha x}[C_{1}e^{\beta ix}+C_{2}e^{i\beta x}]\dots$
>[!example]
>$y''+2y'+y=0$
>$r^2+2r+1=0\implies r_{1,2}=-1$
>$y(x)=C_{1}e^{-x}+C_{2}xe^{-x}$

