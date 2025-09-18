# Question 1

A double-stranded no. $60$ roller chain is used to transmit power between a $13$-tooth driving sprocket at $300$ rev/min and a $52$-tooth driven socket

>[!information]
>$2$ strand
>No.$60$ chain
>$n_{1}=300$rpm
>Driving teeth $N_{1}=13$
>Driven teeth $N_{2}=52$

## Part a.
What is the allowable horsepower?

$H_{a}=K_{1}K_{2}H_{tab}$

From table 17-20, $H_{tab}=6.20$, from table 17-20, we can see that we are in pre-extreme hp
From table 17-22, $K_{1}=0.75$
From table 17-23, $K_{2}=1.7$ since this is a double roller

$\implies H_{a}=H_{tab}\cdot K_{1}\cdot K_{2}=7.905\text{hp}$

## Part b.
Determine the centre-to-centre distance if the chain length is $82$ links ( pitches )

$\frac{L}{p}=82$

From table 17-19 pitch $=0.750$
Equation 17-36: $A=\frac{N_{1}+N_{2}}{2}-\frac{L}{p}$
Equation 17-35: $c=\frac{p}{A}\left[ -A+\sqrt{ A^{2}-8\left( \frac{N_{2}-N_{1}}{2\pi} \right)^{2} } \right]$
$A=\frac{13+52}{2}-82=-49.5$
$c\approx 18$in

## Part c.
Determine the torque and chain tension if the power transmitted is $30$% less than the corrected (allowable) power

$H=H_{a}\cdot 70\%=5.53$hp
$T\omega=H$
$w=\frac{2\pi n}{60}=31.4$ rad/s
$T=\frac{H}{\omega}=1163$ lb-in
Now for the tension $T=D\cdot \frac{PD_{1}}{2}$

From Equation 17-29: $PD_{1}=\frac{p}{\sin\left( \frac{180^{\circ}}{N_{1}} \right)}$
$PD_{1}=\frac{0.75\text{in}}{\sin\left( \frac{180^{\circ}}{N_{1}} \right)}=3.13$ in
$F=\frac{2T}{PD_{1}}=742$ lbf

# Question 2

A four stranded no. $40$ roller chain transmits power from a $21$ tooth driving sprocket to an $84$ tooth driven sprocket. The angular speed of the driving sprocket is $2000$rpm

>[!information]
>$4$ strand
>No.$40$ chain
>$N_{1}=21$
>$N_{2}=84$
>$n_{1}=8000$


## Part a.

if the centre-to-centre distance needs to be $20$ in what is the chain length?

$c=20,\quad L=?$

From Equation 17-34:  $\frac{L}{p}\approx \frac{2c}{p}+\frac{N_{1}+N_{2}}{2}+\frac{(N_{2}-N_{1})^{2}}{\frac{4\pi^{2}c}{p}}$
From table 17-29:  $p=0.5$ in
$\implies L=67.5$ in

## Part b. 

Determine the tabulated horsepower

$H_{a}=?,\qquad H_{a}=K_{1}K_{2}H_{tab}$

From table 17-20:  $H_{tab}=7.72$ hp
From table 17-22:  $K_{1}$ in the post-extreme region $=\left( \frac{N_{1}}{17} \right)^{1.5}=1.84$
From table 17-23:  $K_{2}=3.3$
$\implies H_{a}=34.9$ hp

## Part c.

Estimate allowable horsepower from Equation 17-32 and 17-33 which are the sources for table 17-20 and compare with value found in [[Tutorial 1#Part b. | Part b.]]  

Equation 17-32:  <u><b>Link plate failure</u> </b>
$$H_{1}=K_{lp}N_{1}^{1.08}n_{1}^{0.9}p^{3-0.07p}\cdot K_{2}$$
$K_{lp}=\begin{cases}0.0022 \sim \text{no.}41 \\ 0.0040 \sim \text{other}\end{cases}$
Plug in values to get $H_{1}=12.8K_{2}=42.4$ hp

>[!note]
>There is something weird about this calculation, the numbers don't give that answer but TA said the answer is correct

Equation 17-33:  <u><b>Roller pin failure</u></b>

$$H_{2}=1000K_{r}N^{1.5}p^{0.8}n_{1}^{-1.5}\cdot K_{2}$$
$K_{r}=\begin{cases}2.8 & \sim & \text{no.}25,35 \\ 3.4 & \sim & \text{no.}41 \\ 17 & \sim & 20-240\end{cases}$

$\implies K_{r}=17$

$H_{2}=10.5K_{2}=34.7$ hp

As we can see the failure is going to be roller pin failure for this system

## Part d.

What is the tension using the result from [[Tutorial 1#Part b. | Part b.]]

$F=?$

$T=\frac{H}{\omega} \quad \quad \omega=\frac{2\pi n}{60}=209.4$ rad/s

$T=\dots=1096$ lb-in

$F=\frac{2T}{PD_{1}}$
From equation 17-29:  $PD_{1}=\frac{P}{\sin\left( \frac{180^{\circ}}{N_{1}} \right)}=3.36$ in
$\implies F=654$ lbf


# Question 3.

A **six** inch wide polyamide F-1 flat belt connects a 2 in diameter pulley to drive a larger pullet with an angular velocity ratio of 0.5. The centre-to-centre distance is nine feet, the 
angular velocity of the small pulley is $1750$ rev/min as it delivers $2$hp. The application is such that a service factor $K_{s}$ of $1.25$ is appropriate

## Part a.

Find $F_{c},F_{i},F_{1a},\&F_{2}$

$F_{c}\equiv$ tension from centrifugal force
$F_{1}\equiv$ initial tension
$F_{1a}\equiv$ largest allowable tension
$F_{2}\equiv$ loose side tension

From equation 17-8e:  $F_{c}=\frac{W}{g}\cdot \left( \frac{v}{60} \right)^{2}$
$v=\frac{2\pi n}{60}\cdot \frac{d_{1}}{2}=183.3$ in/s $=916$ ft/min
$W=\gamma bt\cdot \frac{12\text{in}}{1\text{ft}}$
$t\equiv$ thickness of belt
$b\equiv$ belt width $=6$in

From table 17-2:
	$t=0.05$in
	$\gamma=0.095 \frac{\text{lbf}}{\text{in}^{3}}$
	$F_{a}=35 \frac{\text{lbf}}{\text{in}}$
	$f=0.5$
$\implies W=0.025\cdot 6 \cdot 0.05 \cdot 12= 0.126 \frac{\text{lbf}}{\text{ft}}$
$\implies F_{c}= \frac{0.126}{32.17}\cdot \left( \frac{916}{60} \right)^{2}=0.913$lbf

From equation 17-8h: $F_{1a}-F_{2}=\frac{2T}{d}$
$T=\frac{H}{\omega}$

From equation 3-42:  $H=H_{nom}\cdot K_{s}n_{d}$
$n_{d}\sim$ design factor
$n_{d}=1$
$T=\frac{63025\cdot H_{nom}K_sn_{d}}{n}=90$lbf-in
$F_{2}=F_{1a}-\frac{2T}{d}=147-2\cdot \frac{90}{2}=57$lbf

From equation 18-8i:  $F_{i}=\frac{F_{1}+F_{2}}{2}-Fc=101.11$lbf

## Part b.

What is $H_{a}$

From equation 17-11j:  $H_{a}=\frac{(F_{1a}-F_{2})V}{33,000}=2.5$hp

## Part c.

What is the factor of safety $n_{fs}=?$

$n_{fs}=\frac{H_{a}}{H_{nom}K_{s}}=1$

## Part d. 

What is the belt length?

From equation 17-2:  
$$L=\sqrt{ 4c^{2}-(D-d)^{2} }+\frac{1}{2}(D\phi_{D}+d\phi_{d})$$
$\frac{d}{D}=VR =0.5\implies D=4$in

$\phi_{d}=\pi-2\arcsin\left( \frac{D-d}{2c} \right)=3.12$rad
$\phi_{D}=\pi+2\arcsin\left( \frac{D-d}{2c} \right)=3.16$rad

$\implies L=225$in

## Part e.

Find belt dip

From equation 17-13:  dip$=\frac{c^{2}W}{96F_{i}}=\frac{(9\cdot 12)^{2}(0.126)}{96*101.1}=0.151$in