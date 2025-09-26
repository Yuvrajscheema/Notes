# Question 1

A mine hoist uses a $2$in $6 \times 19$ moniter-steel wire rope. The rope is used to haul maximum loads of $4$ tones from a $480$ ft. shaft. The drum has a diameter of $6$ feet and the sheaves are of a good-quality cast steel, and the smallest diameter is $3$ feet in diameter

>[!information]
>monitor steel
>$2$-in $6\times 19$
>maximum load is $8000$lbf
>

## Part a

Using a maximum hoisting speed of $1200$ feet/minute and a maximum acceleration of
$2$ft/$\text{s}^{2}$, estimate the stresses in the wire rope

>[!information]
>acceleration $=\frac{2ft}{s^{2}}$
>speed $=\frac{1200ft}{\text{min}}$
>$1: F_{t}\sim$ tension limit
>$2: F_{b}\sim$ bending
>$3: F_{f}\sim$ fatigue

### Part 1

From equation 17-47: tensile wire load
$$F_{t}=\left( \frac{W}{m}+wl \right)\left( 1+\frac{a}{g} \right)$$
$W\sim$ weight supported: $8000$lbf
$w\sim$ weight of the rope per length
$l\sim$ length of the rope
$m\sim$ number of ropes

From table 17-24: $w=1.60d^{2}=1.60\cdot 2^{2}$
$F_{t}=11,760\text{in-lbf}$

$(S_{u})_{nom}=106\text{kpsi}$
$(S_{u})_{nom}<S_{u}$ (on page 922)
$(S_{u})_{nom}$ is over entire are, not just area of metal in the rope

From table 17-27
Area of metal
$A_{m}=0.40d^{2}=1.6\text{in}^{2}$

Ultimate load

$F_{u}=(S_{u})_{nom}\times A_{nom}$
$A_{nom}=\frac{\pi}{4}d^{2}$
$F_{u}=333\text{kip}$

### Part 2

Equation 17-41: equivalent bending load
$$F_{b}=\frac{E_{r}d_{w}A_{m}}{D}$$
Better sheave diameter
$D=45d=90\text{in}$
$E_{r}\sim$ Young's modulus $=12\times 10^{6}\text{psi}$
$d_{w}=0.067d^{2}=0.0134\text{in}$
$\implies F_{b}=28,600\text{lbf}$

### Part 3.

From equation 17-44: Fatigue Tension

$$F_{f}=\frac{\frac{p}{S_{u}}S_{u}dD}{2}$$
From figure 17-21: Endurance limit/fatigue life
Pressure-strength ratio: $1000 \frac{p}{S_{u}}$
Assuming a million bends until failure
First calculate for infinite - life $\implies 1,000,000 \text{cycles}$
$1000\frac{p}{S_{u}}=1.4\implies \frac{p}{S_{u}}=0.0014$
$240<S_{u}<280\text{ kpsi}$
$S_{u}=240\text{ kpsi}$
$F_{f}=30,300\text{ lbf}$

## Part b

Estimate the various factors of safety

Static with bending 
$n_{fs}=\frac{F_{u}-F_{b}}{F_{t}}=\frac{333,000-28,600}{11,760}=$
$n_{fs}=\frac{F_{u}}{F_{t}}=\frac{333,000}{17,60}=28.3$ static without bending
Fatigue without bending $n_{fs}=\frac{F_{f}}{F_{t}}=2.57$
Fatigue with bending $n_{fs}=\frac{F_{f}-F_{b}}{F_{t}}=0.14<1$
Lets try $100,000\text{ cycles}$ instead
$\frac{F_{f}-F_{b}}{F_{t}}=4.91$

# Effective friction equations

Equation 17-7

$$f'=\frac{1}{\phi}\ln \frac{((F_{1})_{a}-F_{c})}{F_{2}-F_{c}}$$
If you complete question 2 you get $f'=0.656<f=0.8$ so the belt doesn't slip

