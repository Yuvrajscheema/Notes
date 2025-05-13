## #1
$mx''+cx'+kx = f(t)$
$p = \frac{c}{2m}, \omega_{1}^{2} = \frac{k}{m} - p^2$
Take L.T.
$ms^{2}X+csX+kX= F(s)$
$X = \frac{1}{m((s+p)^{2}- \omega_{1}^{2)}} \cdot F(s)$
$x(t) = \int_{0}^{t}f(\tau)\frac{1}{m\omega_{1}^2}e^{-p\tau}\sin{(\omega_{1}(t - \tau))}d\tau$
## #2
$x''+4x'+5x = \delta(t - \pi)$
Take L.T.
$s^{2}X- 2 +4sX+5X = e^{-\pi s}$
$X = \frac{2}{s^{2}+4s+5}+ \frac{e^{-\pi s}}{s^{2} + 4s +5}$

$X = \frac{2}{(s+2)^{2}+ 1} + e^{-\pi s} \cdot \frac{1}{(s+2)^2+1}$
$x(t) = e^{-2t}2\sin{t)} + u(t - \pi)e^{-2t}\sin{t}$
## #3
$x''+4x'+3x = 2\delta(t - \pi)$
$Xs^{2}-2s+4Xs- 2 +3X = 2e^{-\pi s}$
$X = \frac{2}{s^{2}+4s+3}+\frac{2s}{s^{2}+4s+3} +2e^{-\pi s} \cdot \frac{1}{s^2+4s+3}$
$X = \frac{2}{(s+2)^{2} - 1} +\frac{2s}{(s+2)^{2} - 1} + 2e^{-\pi s} \cdot \frac{1}{(s+2)^{2} - 1}$
$x(t)= 2e^{-2t}\sinh{t}+2e^{-2t}\cosh{t}+u(t-\pi)e^{-2t}\sinh{t}$
## #4
$x_{2}' = x_{2}$
$\Longrightarrow x_{2} = C_{1}e^t$
$x_{1}' = x_{2} -x_{2} + t$
$x_{1}'+x_{1} = C_{1}e^{t} + t$ 
Solve via integrating factor
$r = e^{\int 1dt} = e^t$
$\frac{d}{dt}(e^{t}x_{1}) = C_{1}e^{2t}+te^{t}$
$e^{t}x_{1} = \int C_{1}e^{2t}+te^{t}dt$
$e^{t}x_{1} = \frac{C_{1}}{2}e^{2t} +te^{t} - e^{t}+C_{2}$
$x_{1} = \frac{C_{1}}{2}e^{t}+t-1+C_{2}e^{-t}$

