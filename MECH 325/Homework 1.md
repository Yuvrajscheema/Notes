Answers to problems are denoted with a $\star$
# Problem 1
A $12$ inch wide Polyamide A-3 flat-belt drive is to connect a $5$ inch diameter pulley to drive a larger pulley with a velocity reduction ratio of $0.5$. The center line distance is $20$ feet. The small pulley turns at $1750$ rpm as it delivers $3$HP. Use a service factor Ks = $1.25$ and design factor of $1.0$

>[!information]
>$b=12\text{in}$
>Belt type, Polyamide A-3 flat belt
>$d_{1}=5\text{in}$
>$VR=0.5$
>$c=20\text{ft}$
>$n=1750$
>$H_{nom}=3\text{Hp}$
>$K_{s}=1.25$
>$n_{d}=1$



## Part a.

Find $F_{c}, F_{i}, (F{1})_{a}$ and $F_{2}$ assuming operation at maximum tension limit

$F_{c}=\frac{W}{g}\cdot\left( \frac{v}{60} \right)^{2}$
$W=\gamma bt$
$b=12\text{in}$
From table 17-2
$\gamma=0.042$
$t=0.13$
$\implies W=0.042\cdot12\cdot0.13\cdot12=0.7862\text{lbf/ft}$
$v={2\pi n}\cdot \frac{d_{1}}{2} \cdot \frac{1}{12}=2291\text{ft/min}$
$\implies F_{c}=35.6\text{lbf}\quad\star$

$F_{1a}-F_{2}=\frac{2T}{d}$

$T=\frac{H}{\omega}$
$T=\frac{{63025\cdot H_{nom}\cdot K_{s}\cdot n_{d}}}{n}=135\text{ lbf-in}$
$F_{1a}=b\cdot F_{a}\cdot C_{v}\cdot C_{p}$
$F_{a}=100$
$C_{v}=1$
$C_{p}=0.7$
$F_{1a}=840\quad\star$

$\implies F_{2}=F_{1a}-\frac{2T}{d}=786\text{ lbf} \quad \star$

$F_{i}=\frac{{F_{1a}+F_{2}}}{2}-F_{c}=777\text{ lbf}\quad \star$

## Part b.

Find $H_{a}$, safety factor and belt length

$H_{a}=\frac{{(F_{1a}-F_{2})V}}{33000}=3.75\text{ Hp}$

$n_{fs}=\frac{H_{a}}{H_{nom}\cdot K_{s}}=1$

$L=\sqrt{ 4c^{2}-(D-d)^{2} }+\frac{1}{2}(D\phi_{D}+d\phi_{d})$

$\phi_{d}=\pi-2\arcsin\left( \frac{D-d}{2c} \right)=3.12$rad
$\phi_{D}=\pi+2\arcsin\left( \frac{D-d}{2c} \right)=3.16$rad

$\implies L=504\text{ in}=42\text{ ft}$

## Part c.

Find the belt dip

$\text{dip}=\frac{c^{2}W}{96F_{i}}=0.607\text{ in}$


# Problem 2

DriveR:
	Six cylinder engine
	speed = $1750\text{ rpm}$
	input power = $40\text{ Hp}$
DriveN:
	heavy conveyor
	speed = $550\text{ rpm}$ nominal
	service = $16\text{ Hrs/day}$

Since we have a six cylinder engine driving a heavy conveyor at over 15 hours a day
we get a service factor of $1.4$

$H_{d}=H_{nom}K_{s}=40\cdot 1.4=56\text{ Hp}$

Based on this information we want a 3V belt

$VR=\frac{1750}{550}=3.18$

lets select the smaller sheave diameter

Run the belt at $v\approx4000\text{ ft/min}$ so it is safely within operating range

therefore $d=\frac{12v}{\pi n}=8.73\text{ in}$

Looking at the standard 3V sheave diameters we will pick $d = 7.95\text{ in} \quad \star$
Which gives us a velocity within $\sim{9}1\%$ of the target $4000\text{ ft/min}$

$D = d \cdot VR=25.3\text{ in}$

So now we select the closest standard sheave $D=24.95\text{ in}\quad \star$

which gives an actual velocity ratio of $VR=3.14\quad\star$ which is very similar to the nominal value

Now we find the rated power

Use this equation since its a 3V
$H_{r}=P_{2}+\frac{VR-3.38}{3.38-1}(P_{2}-P_{1})$

We read these from table 17-14 and get

$P_{2}=10.6\quad P_{1}=10$

$\implies H_{r}=10.54$

Now find center distance and belt length
$D<C<3(D+d)\quad\quad{2}4.95<C<98.7$
We choose $C=26\text{ in}$ for now

$L_{p}=2C + 1.57(D+d)+\frac{(D-d)^{2}}{4C}=106.4\text{ in}$
We will choose $L =106\text{ in}$
So now we use $C=\frac{{B+\sqrt{ B^{2}-32(D-d)^{2} }}}{16}$
Where $B=4L-6.28(D+d)=217$
$\implies C=25.8\text{ in}\quad\star$

Now it's time to find the amount of belts needed
$\theta_{d}=\pi-2\arcsin\left( \frac{D-d}{2C} \right) =2.47\text{ rad}=141\degree$
$\theta_{D}=\pi+2\arcsin\left( \frac{D-d}{2C} \right)=3.81\text{ rad}=219\degree$

So now from table lookups

$C_{L}\approx 1.09$
$C_{\theta}\approx{0}.89$
$H_{c}=H_{r}\cdot C_{L}\cdot C_{\theta}=10.2$

$\text{num of belts}\geq \frac{H_{d}}{H_{c}}=5.5\implies\text{num of belts} = 6\quad\star$

# Problem 3

## Part a.

DriveR: AC Motor (Normal Torque)      Speed = 1750rpm            Input Power = 5 HP

DriveN: Fan    Speed = 725 rpm (nominal)               Service= 22 hours/day

Very similar to what was done in question 2

We have a normal torque AC motor running smooth loading at over $15$ hours a day,
this gives us $K_{s}=1.2$

$H_{d}=H_{nom}\cdot K_{s}=5\cdot1.2=6\text{ Hp}$

From figure 17-13 we can see that we will use a 3V belt

$VR=\frac{1750}{725}=2.41$

$v = 4000\text{ ft/min}$
$d=\frac{12v}{\pi n}=8.7308$


Looking at the standard 3V sheave diameters we will pick $d = 7.95\text{ in} \quad \star$
Which gives us a velocity within $\sim{9}1\%$ of the target $4000\text{ ft/min}$

$D=d\cdot VR=19.2\text{ in}\quad$
So we will pick $D=18.95\text{ in}\quad\star$

This gives us a velocity ratio of $VR=2.38\quad\star$ which is very close to the original value


Now we find the rated power

Use this equation since its a 3V
$H_{r}=P_{2}+\frac{VR-3.38}{3.38-1}(P_{2}-P_{1})$

We read these from table 17-14 and get

$P_{2}=10.6\quad P_{1}=10$

$\implies H_{r}=10.35$


Now find center distance and belt length
$D<C<3(D+d)\quad\quad 18.95<C<80.7$
We choose $C=20\text{ in}$ for now

$L_{p}=2C + 1.57(D+d)+\frac{(D-d)^{2}}{4C}=83.75\text{ in}$
We will choose $L =85\text{ in}$
So now we use $C=\frac{{B+\sqrt{ B^{2}-32(D-d)^{2} }}}{16}$
Where $B=4L-6.28(D+d)=171$
$\implies C=20.7\text{ in}\quad\star$

Now it's time to find the amount of belts needed
$\theta_{d}=\pi-2\arcsin\left( \frac{D-d}{2C} \right) =\dots=149\degree$
$\theta_{D}=\pi+2\arcsin\left( \frac{D-d}{2C} \right)=\dots=211\degree$

So now from table lookups

$C_{L}\approx 1.04$
$C_{\theta}\approx{0}.92$
$H_{c}=H_{r}\cdot C_{L}\cdot C_{\theta}=9.9$

$\text{num of belts}\geq \frac{H_{d}}{H_{c}}=0.6\implies\text{num of belts} = 1\quad\star$

## Part b.

This is the exact same as [[Homework 1#Part a.| Part a.]] but now using different values since we are using Gates manual instead
This section will look the exact same as the last but values will differ


We have a normal torque AC motor running a fan under $10\text{ Hp}$ at over $16$ hours a day,
this gives us $K_{s}=1.3$

$H_{d}=H_{nom}\cdot K_{s}=5\cdot1.3=6.5\text{ Hp}$

With this design power we will choose a V3 belt

Now lets calculate desired speed ratio and use that to find the sheave diameters and centre distance
$VR=2.41\quad\star$

From Table B6 we lookup the corresponding sheaves

$d=3.35\text{ in}\quad\star$ this is above the NEMA recommended minimum diameter
$D=8.00\text{ in}\quad\star$

We now choose a centre distance $C=12.1\text{ in}\quad\star$
So our belt type is a 3V425 $\star$
$L_{p}=42.5\text{ in}$


This corresponds to a horsepower correction factor of $H_{Ks}=0.9$

Now we will find the basic horsepower per belt from table number B9

$H_{tab}=2.80$
Now we look at the additional power because of the speed ratio
$H_{add}=0.36$

So our horsepower per belt is given by $H_{a}=H_{Ks}\cdot(H_{tab}+H_{add})=2.84\text{ Hp}$

So now we get our number of belts
$\text{num of belts}\geq\frac{H_{d}}{H_{a}}=2.3$ so we will use 3 belts $\star$

>[!comparison]
>In both cases the belt type was the same using a 3V
>For the Gates case we ended up with much smaller sheaves and a more accurate speed ratio with a smaller centre line distance but we also need 3 belts instead of 1


Fromula D19
$T_{st}=15\left( \frac{2.5-K_{\phi}}{K_{\phi}} \right)\left( \frac{\text{motor hp}\cdot 10^3}{N_{b}v} \right)+\frac{Mv^{2}}{10^{6}}$

Table D27
$M=0.46$

Table D26 using linear interpolation
$K_{\phi}=0.943$

$v=n\cdot d\cdot \frac{\pi}{12}=1534\text{ ft/min}$
$\implies T_{st}=29.125$ per belt
The tension for the system is $3T_{st}=87.4\text{ lbf}\quad\star$

Formula D
$t=c\left[ 1-0.125\left( \frac{D-d}{2} \right)^{2} \right]=11.876\text{ in}$
$\text{deflection}=\frac{t}{64}=0.186\text{ in}\quad\star$


# Problem 4

Redo question 3a but using a timing belt and reduce the output speed to $700\text{ rpm}$


DriveR: AC Motor (Normal Torque)      Speed = 1750rpm            Input Power = 5 HP

DriveN: Fan    Speed = 700 rpm (nominal)               Service= 22 hours/day


From table 7-8 we get the service factor $K_{s}=1.5$

$H_{d}=H_{nom}\cdot K_{s}=7.5\text{ Hp}$

From figure 7-27:
we will use $8\text{mm}$ belt pitch $\star$

$VR=\frac{n}{N}=2.5$

from table 7-7
we have 36 driver teeth $\star$
and 90 driven teeth $\star$
 so then
 sprocket num P36-8MGT-30 $d=3.609\quad\star$
 sprocket num P90-8MGT-30 $D=9.023\quad\star$
 we will use a $30\text{ mm}$ wide belt $\star$
 belt 1120-8MGT 140 teeth $C=11.82\text{ in}\quad\star$

From table 7-11 we get the belt correction factor
$C_{L}=1$
$H_{a}=H_{d}\cdot C_{L}=7.5$

The base rated horsepower for the smaller sprocket is $24.9\text{ Hp}$
so we are okay


now the speed of the belt $v=\frac{\pi nd}{12}=1654\text{ ft/min}$
which is in the okay range of less than $6500\text{ ft/min}$
so the system we selected works

# Problem 5

Roller chain is to be used in a hydraulic forklift truck to elevate the forks. If two strands support the load equally which size would you specify for a design load of 2.5 Tonnes? What will be your final safety factor?

we need to lift $5,512\text{ lb}$

Since we have two strands the support the weight equally we have
$2,756\text{ lbf}$ per chain

we want each chain to be able to lift more than that
A number 40 chain has an average tensile stress of $3700\text{ lbf}$     $\star$
So we have a factor of safety of $n_{fs}=1.34\quad\star$

# Problem 6

Design a chain drive to provide the required power and speed to the machinery in design problem 7-41. Specify the chain size, the sizes and number of teeth in the sprockets, the number of chain links (pitches), lubrication requirements, and the center line distance.

DriveR: 6 Cylinder Engine               Speed = 500rpm        Input Power = 40 HP

DriveN: Heavy Conveyor              Speed  = 250  rpm (nominal)


We have an internal combustion engine with moderate shock so that gives us $K_{s}=1.4$

$H_{d}=H_{nom}\cdot K_{s}=56\text{ Hp}$
$VR=\frac{n}{N}=2$
The best choice here seems to be a $N_{1}=35$ tooth sprocket $\star \quad\quad$ 
and a number 80 chain with a horsepower rating of $60.05\text{ Hp}\quad\star$

This chain setup requires bath or disc lubrication $\star$

pitch is $p=1.00\text{ in}\quad\star$
$N_{2}=N_{1}\cdot VR=70$ tooth sprocket $\star$
This keeps the original velocity ratio which is good

Now to calculate $C$ use a trial value of $C=40$ pitches

$L_{c}=2\cdot C+\frac{{N_{2}+N_{1}}}{2}+\frac{(N_{2}-N_{1})^{2}}{4\pi^{2}C}=133.27\text{ pitches}$
so we will use $L_{c}=134\text{ pitches}\quad \star$
$C=\frac{1}{4}\left[ L_{c}-\frac{N_{2}+N_{1}}{2}+\sqrt{ \left[ L_{c}-\frac{N_{2}+N_{1}}{2} \right]^{2}-\frac{8(N_{2}-N_{1})^{2}}{4\pi^{2}} } \right]=40.4\text{ pitches}$
$C=p\cdot 40.4\text{ pitches}=40.4\text{ in}\quad\star$


# Problem 7

A 700 rev/min 25-hp squirrel-cage induction motor is to drive a two-cylinder reciprocating pump, out-of-doors under a shed. The nominal pump speed is 140 rev/min. Select a suitable number of strands of Number 80 chain and sprocket sizes.

$VR=5$

$H_{tab}=31.0\text{ Hp}$ from table 17-20
$H_{d}=H_{nom}\cdot K_{s}\cdot n_{d}$
$n_{d}=1$
$K_{s}=1.3$
$H_{d}=32.5\text{ Hp}$

We are operating in pre extreme region

lets choose $N_{1}=24\quad\star$
$N_{2}=120\quad\star$
$p=1\text{ in}\quad\star$
$\implies K_{1}=\left( \frac{N_{1}}{17} \right)^{1.08}=1.45$
We will see if we need $K_{2}$

$H_{a}=H_{tab}\cdot K_{1}\cdot K_{2}=45.0\text{ Hp}$
$\frac{H_{a}}{H_{d}}=1.38K_{2}$ so it is fine that we only use one chain $\star$


# Problem 8

A 2000-ft mine hoist operates with a 72-in drum using 6 ×19 monitor-steel wire rope. The cage and load weigh 8000 lbf, and the cage is subjected to an acceleration of 2 ft/s2 when starting.

>[!information]
>$200\text{ ft}$ hoist
>$72\text{ in}$ drum
>$F=8000\text{ lbf}$
>6x19 monitor steel wire rope
>$a_{0}=2\text{ ft/s}^{2}$

## Part a.

For a single-strand hoist how does the factor of safety $n_{f}  = F_{f} /F_{t}$, neglecting bending, vary with the choice of rope diameter?


From equation 17-47: tensile wire load
$$F_{t}=\left( \frac{W}{m}+wl \right)\left( 1+\frac{a}{g} \right)$$
$W\sim$ weight supported: $8000\text{ lbf}$
$w\sim$ weight of the rope per length 
$l\sim$ length of the rope
$m\sim$ number of ropes

$w=1.6d^{2}$
$l=200\text{ ft}$
$m = 1$

$F_{t}=8497.4+339.9 \cdot d^{2}$


$F_{f}=\frac{\frac{p}{S_{u}}S_{u}dD}{2}$

$D=72$
$240<S_{u}<280\text{ kpsi}$
$S_{u}=240\text{ kpsi}$

find $\frac{p}{S_{u}}$ for one million cycles aka infinite cycles

$\frac{p}{S_{u}}=0.0014$

$\implies F_{f}=12.096d\text{ kip}=12096d\text{ lbf}$
$n_{fs}=\cfrac{12,096d}{8497.4+339.9d^{2}}$
We can plot this to get the following

![[Homework_1_question_8_a.png]]

As we can see, increasing the diameter increases the factor of safety $\star$ on a logarithmic scale
For the diameter we will use the better sheave diameter formula with $d=\frac{D}{45}=1.6\text{ in}$ which corresponds to a safety factor of $\sim{2}\quad\star$

## Part b.

Let $m=4$ now, how does the factor of safety change with the diameter

All that changes is $F_{t}$
And now redoing the equation we get $F_{t}=2124.3+339.9d^{2}$
so now we have the following

$n_{fs}=\cfrac{12,096d}{2124.3+339.9d^{2}}$
which when plotted looks like the following
![[homework_1_question_8_b.png]]As we can see the diameter increases the factor of safety until the diameter becomes greater than $2.5\text{ in}$ and then it starts to decrease $\star$

For the diameter we will use the better sheave diameter formula with $d=\frac{D}{45}=1.6\text{ in}$ which corresponds to a safety factor of $\sim{6.5}\quad\star$

## Part c.

Would you expect your chosen diameter in part (a) to change depending on the end fitting selected (say flemish eye splice versus wire rope clips)? For  the wire rope clips specify the number of clips, torque required, and minimum tie back required.

My chosen diameter would not need to change based on flemish eye splice since they are $92.5\%$ efficient so the factor of safety stays comfortably above $1\quad\star$

For the wore rope clips the diameter still doesn't need to change since $2\cdot {0}.8=1.6>1$ so the factor of safety is still above $1\quad\star$

The number of clips can be determined using the tables in the wire rope slide deck

Since our $d=1.6$ then we need at least $8$ clips$\quad\star$

The torque required is $430\text{ ft-lbs}\quad\star$

The minimum number of tie back is $58\text{ in}\quad \star$