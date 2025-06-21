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

## Cauchy-Euler ODE
- Of the form $x^2y''+axy'+by=0$, $y(x)=x^r$
- $(r^{2}(r-1)+ar+b)x^{r}=0$ if $x^{r}\neq {0}$
- So then the characteristic equation is $r^{2}(r-1)+ar+b=0$
- $r=\frac{-(a-1)\pm \sqrt{ (a-q)^{2}-4b }}{2}$
- **1.** positive discriminant gives two distinct roots, $r_{1},r_{2}$
- $y(x)=C_{1}x^{r_{1}}+C_{2}x^{r_{2}}$
- **2.** negative discriminant, two complex roots, $r_{1}=\alpha+\beta i,r_{2}=\alpha-\beta i$
- $y(x)=x^\alpha[C_{1}x^{i\beta}+C_{2}x^{-i\beta}]=x^{\alpha}[C_{1}e^{i\beta \ln x}+C_{2}e^{-i\beta \ln x}]$ this gives us $x^{\alpha}[C_{1}\cos(\beta \ln x)+C_{2}\sin(\beta \ln x)]$
- **3.** discriminant is equal to zero, $r_{1},r_{2}=r$
- $y_{1}(x)=x^r$, $y_{2}(x)=\frac{ \partial  }{ \partial r }y_{1}(x,r)$
	- $y(x,r)=x^{r}=e^{r\ln x}=\ln x \cdot x^{r}$
# Power Series Method
- $P(x)y''+Q(x)y'+R(x)y=0$
- Typically use numerical methods
- Given a function $f(x)$ we approximate this function with the power series approximation $f(x) \approx \sum_{n=0}^{n}a_{n}x^n$
- The power series is $f(x)=\sum_{n=0}^{\infty }a_{n}x^{n}$
- If $f(x)$ is analytic $f(x)=\sum \frac{f^{(n)}(x_{0})}{n!}(x-x_{0})^n$ this is the taylor series, if $x_{0}=0$ then $f(x)=\sum \frac{f^{n}(0)}{n!}x^n$
- This is only useful if the power series converges so lets look at the **convergence**
- $f(x)=\sum a_{n}x^{n}$ converges if $l=\lim_{ N \to \infty }\sum_{n=0}^{N} a_{n}x^n$
- If $R=0$ then the series only converges around $x_{0}$
- If $l$ is finite then the power series converges in the interval $x_{0}-R,x_{0}+R$ where $R$ is the radius of convergence, $R$ is finite
- If $R \to \infty$ then the series converges everywhere
- We can prove the convergence with the **ratio test
- The power series $f(x)=\sum_{n=0}^{\infty }a_{n}(x-x_{0})^{n}=\sum b_{n}$ converges if $\lim_{ n \to \infty }| \frac{b_{n+1}}{b_{n}} |=l<1$
>[!example]
>$f(x)=\sum \frac{1}{n!}x^n$
>$b_{n}=\frac{x^n}{n!}$; $b_{n+1}=\frac{x^{n+1}}{(n+1)!}$
>$\lim_{ n \to \infty } |\frac{n!}{(n+1)!}|\cdot|x|=0$
>So then the series converges for all real numbers

>[!example]
>$f(x)=\sum \frac{(x-1)^{2n}}{4^n}$
>$\lim_{ n \to \infty } | \frac{(x-1)^{2n+2}}{4^{n+1}}\cdot \frac{4^{n}}{(x)^{2n}}$
>$|\frac{(x-1)^{2}}{4}| \lim_{ n \to \infty }1 \implies |\frac{(x-1)^{2}}{4}|<1$
>Which means that $|x-1|<2$ so $R=2$ centerd at $x_{0}=1$
>So the interval of convergence is $(-1,3)$


- Now to **solve** the ODE $P(x)y''+Q(x)y'+R(x)y=0$ with the power series
- Let $y(x)=\sum a_{n}(x-x_{0})^n$, $y'=\sum a_{n}n(x-x_{0})^{n}$, $y''=\sum a_{n}n(n-1)(x-x_{0})^n$
>[!example]
>$y'-y=0$, the solution to this is clearly $y=Ce^x$ but lets use power series
>$y(x)=\sum a_{n}x^{n}$, $y'=\sum a_{n}nx^{n-1}$
>So then we have $\sum_{n=1} a_{n}nx^{n-1}-\sum a_{n}x^{n}=0$, let $m=n-1$
>$\sum_{m=0}^{\infty}a_{m+1}(m+1)x^{m}-\sum_{m=0}^{\infty}a_{m}x^{m}=0$ Now we can combine these series into one series
>$\sum_{m=0}^{\infty}[a_{m+1}(m+1)-a_{m}]x^{m}=0$, this is only possible if $a_{m+1}(m+1)-a_{m}=0$
>$a_{m+1} = \frac{a_{m}}{m+1}$ for $m=1,2,3,\dots$, recursive relation
>$a_{0}$ is arbitrary
>$m=0\implies a_{1}=a_{0}$
>$m=1\implies a_{2}=\frac{a_{1}}{2}=\frac{a_{0}}{2}$
>$m=2\implies a_{3}=\frac{a_{2}}{3}=\frac{a_{1}}{6}=\frac{a_{0}}{6}$
>$m=n\implies a_{m+1}=\frac{a_{0}}{(m+1)!}$
>So $y(x)=a_{0}+a_{1}x+\frac{a_{2}x}{2}+\dots=a_{0}\left( 1+x+\frac{x^2}{2}+\dots \right)$
>$y(x)=Ce^x$
>Now you can very easily find the radius of convergance

>[!example]
>$x^{2}y'-y=0$ we will solve this classically and with the power series
>$\frac{dy}{y}=x^{-2}dx$
>$\ln y=-\frac{1}{x}+C$
>$y=Ae^{-1/x}$
>Now lets try the power series method, $y(x)=\sum_{n=0}^{\infty} a_{n}x^{n}$
>$y'=\sum_{n=1}^{\infty} a_{n}nx^{n-1}$
>Now plug this into the equation:
>$\sum_{n=1}^{\infty}a_{n}nx^{n+1}-\sum_{n=0}^{\infty}a_{n}x^{n}=0$, let $m=n+1$
>Now we have the following
>$\sum_{m=2}^{\infty}a_{m-1}(m-1)x^{m}-\sum_{n=0}^{\infty}a_{n}x^{n}=0$
>$\sum_{m=2}^{\infty}a_{m-1}(m-1)x^{m}-\sum_{n=2}^{\infty}a_{n}x^{n}-a_{0}x^{0}-a_{1}x^{1}=0$
>$-a_{0}-a_{1}x^{1}+\sum_{m=2}^{\infty}[a_{m-1}(m-1)-a_{m}]x^{m}$
>this equation only holds if $a_{0}=0$ and $a_{1}=0$
>$a_{m}=a_{m-1}(m-1)$, $m=2,3,4\dots$
>$m=2\implies a_{2}=a_{1} \cdot_{1}=0$
>$a_{m}=0\forall m$
>$y(x)=0$
>The difference between the results are caused by $x=0$ being a singular point
- Power series method is only valid at **ordinary points**
>[!definition]
>Given $P(x)y''+Q(x)y'+R(x)y=0$
>A point $x_{0}$ is an ordinary point of the equation if $p(x)=\frac{Q(x)}{P(x)}$ and $q_{1}(x)=\frac{R(x)}{P(x)}$$ are analtic at $x0$
>i.e. $p(x)=p_{0}+p_{1}(x-x_{0})+p_{2}(x-x_{0})^{2}+\dots$, $q_{1}(x)=q_{1,0}+q_{1,1}(x-x_{0})+q_{1,2}(x-x_{0})^2$
>If a point is an ordinary point then the power series will work!

>[!example]
>$y''-\sqrt{ x }y'+xy=0$
>$p(x)=-\sqrt{ x },\quad q_{1}(x)=x$
>$x=0$ is a singular point as the derivative is not defined there

>[!example]
>$x^{2}y'-y=0$
>$x=0$ is a singular point as the derrivatve is not defined there, $x=1$ is an ordinary point, so we get the following
>$x^{2}\sum_{n=1}^{\infty}a_{n}n(x-1)^{n-1}-\sum a_{n}(x-1)^{n}=0$ now we complete the square for $x^2$
>$x^{2}=(x-1)^{2}+2x-1=(x-1)^2+2(x-1)+1$
>Now we have
>$\sum_{n=1}a_{n}n(x-1)^{n+1}+\sum_{n=1}2a_{n}n(x-1)^{n}+\sum_{n=1}a_{n}n(x-1)^{n-1}-\sum a_{n}(x-1)^{n}=0$
>
>

- Given the equation $(x-x_{0})^{2}y''+\alpha(x-x_{0})y'+ y=0$
- So we have $p(x)=\frac{1}{x-x_{0}}$ and $q(x)=\frac{1}{(x-x_{0})^{2}}$
- $P(x)y''+Q(x)y'+R(x)y=0$
- $y''+P(x)y'+q(x)y=0$
- $(x-x_{0})^{2}y''+(x-x_{0})[(x-x_{0})p(x)]y'+(x-x_{0})^{2}q(x)y=0$

>[!Definition]
>A point $x=x_{0}$ is a **regular singular point** if
>$\lim_{ x \to x_{0} }(x-x_{0})p(x)$ and $\lim_{ x \to x_{0} }(x-x_{0})^{2}q(x)$ are finite

>[!Example]
>$(1-x^{2})y''-2xy'+\beta y$
>$x_{0}=\pm_{1}$ are singular points, now we must check if they are regular
>At $x_{0}=1$, $\lim_{ x \to 1 }\left(x-1)[ -\frac{2x}{1-x^{2}} \right]=1$ and $\lim_{ x \to 1 }(x-1)^{2}\left[ \frac{\beta}{1-x^{2}} \right]=0$

>[!definition]
>Forbenius series
> If $x=x_{0}$ is RSP, $y(x)=(x-x_{0})^{r}\sum a_{n}(x-x_{0})^{n}$
$y(x)=\sum a_{n}(x-x_{0})^{n+r}$

>[!example]
>$4xy''+2y'+y=0$
>$x=0$ is a regular singular point
>so $y(x)=\sum a_{n}x^{n+r},\quad y'=\sum a_{n}(n+r)x^{n+r-1}, \quad y''=\sum a_{n}(n+r)(n+r-1)(x^{n+r-2})$
>Now we can plug these derivatives to get the following
>$\sum 4a_{n}(n+r)(n+r-1)x^{n+r-1}+\sum 2a_{n}(n+r)x^{n+r-1}+\sum a_{n}x^{n+r}=0$
>Now we will convert the final term, let $n+r=m+r-1 \implies m=n+1$
>$\sum [4a_{m}(m+r)(m+r-1)+2a_{m}(m+r)]x^{m+r-1}+\sum_{m=1} a_{m}x^{m+r-1}=0$
>The third term can become $\sum_{m=1}^{\infty}a_{m-1}x^{m+r-1}$
>$[4a_{0}r(r-1)+2a_{0}r]{x^{r-1}}\sum_{m=1}(2a_{m}(m+r)[2(m+4-1)+1]+a_{m-1})x^{n+r-1}=0$
>The coefficients of the lowest $x$ power gives you the indicial equation
>$a_{o}[4r(r-1)+2r+0]=0$
>$2r(r-1)+r=0\implies r_{1,2}=0, \frac{1}{2}$
>From the summation we found earlier we have $a_{m}=\frac{-a_{m-1}}{2(m+r)[2(m+r)+1]}$
>This right here is the recurrence relation
>If $r=0$ then $a_{m}=-\frac{a_{m-1}}{2m(2m-1)}$
>$a_{1}=\frac{-a_{0}}{2\cdot 1}$
>$a_{2}=-\frac{a_{1}}{4\cdot3}=\frac{a_{0}}{4!}$
>$y_{1}(x)=x^{r}\sum a_{n}x^{n}=a_{0}+a_{1}x+a_{2}x^{2}+\dots$
>Now do the same with $r=\frac{1}{2}$

- Given $r_{1}$ and $r_{2}$
- Case 1: $r_{1}-r_{2}$ is not an integer, the solution is $y(x)=C_{1}y_{1}(x)+C_{2}y_{2}(x)$
- Case 2: $r_{1}-r_{2}=0$ $y_{2}(x)=\frac{ \partial  }{ \partial r }y_{1}(x,r)\mid_{r=r_{1}}$
	- $y_{1}=c^{r}\sum a_{n}x^{n}$
	- $x^{r}=e^{r\ln x}$
	- Differentiate to get $\ln x\cdot e^{r\ln x}=x^{r}\ln x$
	- $y_{2}(x)=y_{1}\ln x+\sum b_{n}x^{n+r}$
- Case 3: $r_{1}-r_{2}$ is an integer
	- $y_{2}(x)=\frac{ \partial  }{ \partial r }((r-r_{1})y_{1}(x))$
	-  $y_{2}(x)=a\ln (x)y_{1}+\sum bnx^{n+r}$
- $x^{2}y''+xy'+(x^{2}-\alpha^{2})y=0$ this is a **bessel equation** used mainly for vibrations
- $p(x)=\frac{1}{x}$
- $q(x)=\frac{x^{2}-\alpha^{2}}{x^2}$
- $p_{0}=\lim_{ x \to 0 } \frac{x}{x}=1$
- $q_{0}=\lim_{ x \to 0 } \frac{x^2(x^2-\alpha^{2})}{x^2}=-\alpha^{2}$
- $y(x)=\sum a_{n}x^{n+r}$
- $r(r-1)+rp_{0}+q_{0}=0$
- $r(r-1)+r-\alpha^{2}=0\implies r=\pm\alpha$
# Summary
- Review first and second order odes
- Series solutions of odes
	- Taylor series
	- Forbenius series $\to$ regular singular points
- Bessel functions $x^{2}y''+xy'+(x^{2}-\alpha^{2})y=0$, $x=0$ is a regular singular point