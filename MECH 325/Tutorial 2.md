# Question 1

A $60$hp four cylinder internal combustion engine is used to drive a medium-shock brick making machine under a schedule of 2 shifts per day. the drive consists of two $26$ inch sheaves about $12$ feet apart, with a sheave speed of $400$rpm. Select a Gates Rubber V-belt D360 arrangement.

>[!information]
>medium shock
>$H_{nom}=60$hp
>D360 V-belt
>$d=D=26$in
>$n=400rpm$

## Part a.

Determine the number of belts required

$N_{b}\geq \frac{H_{d}}{H_{a}}$

From table 17-11:  $L_{p}=360+3.3=363.3$ this is the pitch length of our belt
From equation 17-16b:  
$$c=0.25\left[ \left( L_{p}-\frac{\pi}{2} \right)(D+d)+\sqrt{ L_{p}-\frac{\pi}{2}(D+d)^{2}-2(D-d)^{2} } \right]$$
$\implies c=140.8\text{in}\approx 12$ft

From table 17-15:  $K_{s}=1.4$
From equation 17-19:  $H_{d}=H_{nom}K_{s}n_{d},\quad n_{d}=1$
$H_{d}=60\cdot 1.4=84$hp

From equation 17-17:  $H_{a}=K_{1}K_{2}H_{tab}$
$K_{1}\equiv$ wrap angle correction factor
$K_{2}\equiv$ belt length correction factor
From table 17-13:  $K_{1}=1.00$ since the  wrap angle is $180^{\circ}$
From table 17-14:  $K_{2}=1.1$
$v=\frac{\pi dn}{12}=2722.7 \frac{\text{ft}}{\text{min}}$
From table 17-12:
This speed is not on the table so we have to do a linear interpolation!!!!!!!!!!!!!!!!!!!!!
at $3000$fpm:  $H_{tab}=18.1$hp
at $2000$fpm:  $H_{tab}=13.9$hp
Therefore $H_{tab}=16.94$hp
$H_{a}=(1)(1.1)(16.94)=18.63$hp per belt
$N_{b}=\frac{H_{d}}{H_{a}}=4.5$ so we will use $5$ belts :D 

## Part b.

Estimate the taut side tension, slack tension, and pre-tension values. What is the factor of safety?

From equation 17-22:  Force transmitted per belt
$\Delta F=\frac{\left( 63025\cdot \frac{H_{d}}{N_{b}} \right)}{n\cdot \frac{d}{2}}=\frac{\left( 63025\cdot \frac{84}{5} \right)}{\frac{400\cdot {2}6}{2}}=203.6$lbf per belt

From equation 17-21:  centrifugal tension
$F_{c}=K_{c}\left( \frac{v}{1000} \right)^{2}$
From table 17-16:  $K_{c}=3.498$
$F_{c}=3.498\cdot \left( \frac{2722.7}{1000} \right)^{2}=25.93$lbf per belt

From equation 17-23:  taut side tension
$F_{1}=F_{c}+\frac{\Delta Fe^{f\phi}}{e^{f\phi}-1}$
From page 902 Shigleys (manufacturer) $f=0.5123$
$\phi=\pi$
$F_{1}=280.4$lbf per belt

From Equation 17-24: slack side tension
$F_{2}=F_{1}-\Delta F$
$F_{2}=76.83$lbf per belt

From Equation 17-25:  pre-tension
$F_{i}=\frac{F_{1}+F_{2}}{2}-F_{c}$
$F_{i}=152.7$lbf per belt

wtf is this class man I am in belt hell

From equation 17-26:  $n_{fs}=\frac{H_{a}N_{b}}{H_{nom}K_{s}}=1.1$


## Part c.

Estimate the life in passes, hours, and days

From equation 17-28:  $t=\frac{N_{p}L_{p}}{720v}$
$N_{p}\equiv$ number of passes

From equation 17-27
$N_{p}=\left[ \left( \frac{K}{T_{1}} \right)^{-b}+\left( \frac{K}{T_{2}} \right)^{-b} \right]^{-1}$

From table 17-17:  Durability parameters
D-belt$=\begin{cases}K=18726\text{N} \text{ or } 4208\text{lbf} \\ b=11.105\end{cases}$

Pg 906
$T_{1}=F_{1}+\frac{K_{b}}{d}$

From table 17-16:  $K_{b}=5680$
$T_{1}=498$lbf

$\implies N_{p}=9.6\cdot{1}0^{9}>10^{9}$ so for some fucking reason $N_{p}=10^{9}$
$\implies t>\frac{10^{9}(363.3)}{720(2722.7)}=185325$hrs $= 16$hrs/day
$\implies t>31.7$ years

# Question 2

Do the same shit from the last question but with Gates Heavy Duty V-Belt Design Manual

## Part a.
Pg B2
Table B1 $K_{s}=1.5$
$H_{d}=H_{nom}K_{s}=90$hp

Pg B3 Choose CP belt
Table B3 $d>12$ so lets pick $d=13$ because we are like that

Pg B191-Table B23

We are going to select a CP330 belt based off the table
$c=145>144$
This also gives us our horsepower correction factor also or service factor $K_{s}=1.2$

$v=\frac{\pi dn}{12}=1361$ fpm

$H_{a}=K_{s}H_{tab}$
Pg B230 - Table B33:  $H_{tab}=23.3$hp

$\implies H_{a}=1.2\cdot 23.3=27.96$hp
$\implies N_{b}=\frac{H_{d}}{H_{a}}=\frac{90}{27.96}=3.22$ so we use 4 belts


## Part b.

What is the factor of safety? Estimate the taut side tension, slack tension, and pre-tension values

All of this is the same as what was done in [[Tutorial 2#Question 1 | Question 1]]
$n_{fs}=\frac{H_{a}N_{b}}{H_{nom}K_{s}}=1.29$

Use C-blet parameters

$\Delta F=545.2$lbf per belt
$F_{c}=3.18$lbf per belt
$F_{i}=409$lbf per belt
$F_{1}=684.9$ lbf per belt
$F_{2}=139.5$lbf per belt

## Part c.

static tension - $T_{st}$

Pg D24 - TableD27
$M= 1.6\quad Y=89$

Pg D24 - Formula D19
$T_{st}=15\left( \frac{2.5-K_{\phi}}{K_{\phi}} \right)\left( \frac{\text{motor hp}\cdot 10^3}{N_{b}v} \right)+\frac{Mv^{2}}{10^{6}}$

Pg D24 - Table D26
$K_{\phi}=1$
$T_{st}=250.9$ lbf

DO NOT USE EQUATION D25

Formula D35:  span length $=t=c\left[ 1-0.125\left( \frac{D-d}{2} \right)^{2} \right]$
$t=c=145$in
deflection $=\frac{t}{64}=2.25$
From equation F20: $F_{min}=\frac{1.4T_{st}+Y}{16}=27.5$lbf
From equation F21: $F_{max}=\frac{1.5T_{st}+Y}{16}=29.1$lbf

