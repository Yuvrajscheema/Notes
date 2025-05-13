# Uniaxial Loading
- $\delta$ is called the extension or deflection and is negative in compression
- $\sigma\equiv \frac{F_{tensile}}{A_{\perp}}$
- $\varepsilon\equiv \frac{\delta}{L_{o}}$
- $E=\frac{\sigma}{\varepsilon}$
- $\delta=\sigma\cdot \frac{L_{0}}{E}$
# Equilibrium
- Relates forces to forces
- Make internal cuts to solve for forces
# Trusses
- Members must be long and thin
## Zero force members
- Consider one member pins
	- Identify all the pins that connect to one member
	- Eliminate those at which an external load or reaction acts
	- At each pin which remains, the connected member is a zero force member
- Consider two member pins
	- Identify all the pins that connect two members
	- Eliminate those at which an external load or reaction acts
	- Eliminate those at which the two connected members are parallel
	- At each pin which remains, the both of the members connected are zero force members
- Consider three member pins
	- Identify all the pins which connect three members
	- Eliminate those at which an external load or reaction acts
	- Eliminate those where none of the members are parallel
	- At each pin which remains, the non-parallel member connected is a zero force member
- <b>Repeat</b>
# Poissons Ratio
- Values from $-1$ to $0.5$
- Properties are the same in all directions for isotropic materials, not for anisotropic
- $\varepsilon=\frac{1}{E}[\sigma_{\parallel}-\nu(\sigma_{\perp_{1}}+\sigma_{\perp_{2}})]$
- $\sigma=\left( \frac{E}{(1+\nu)(1-2\nu)} \right)[(1-\nu)\varepsilon_{\parallel}+\nu(\varepsilon_{\perp_{1}}+\varepsilon_{\perp_{2}})]$
- For small strain we have $\varepsilon_{V}=\varepsilon_{x}+\varepsilon_{y}+\varepsilon_{z}$
- Modulus of rigidity $G=\frac{E}{2(1+\nu)}$
- Bulk modulus $K=\frac{E}{3(1-2\nu)}$
- $\sigma_{0}=\frac{\sigma_{x}+\sigma_{y}+\sigma_{z}}{3}$
- $\sigma_{0}=K\varepsilon_{V}$ not a needed equation
- For most engineering materials small stresses like atm are negligible
# Shear
- $\tau=\frac{V}{A}$
- $\gamma\approx \frac{\delta}{L}$
- For shear stress the first subscript indicates the plane and the second the direction
- $\tau_{xy}=\tau_{yx}$
- $\tau=G\gamma$
# Thermal Equations
- Small strain is valid up to 10%
- $\varepsilon=\frac{1}{E}[\sigma_{\parallel}-\nu(\sigma_{\perp_{1}}+\sigma_{\perp_{2}})]+\alpha_{L}\Delta T$
- $\sigma=\left( \frac{E}{(1+\nu)(1-2\nu)} \right)[(1-\nu)\varepsilon_{\parallel}+\nu(\varepsilon_{\perp_{1}}+\varepsilon_{\perp_{2}})]-\left( \frac{E}{1-2\nu}\right)\alpha_{L}\Delta T$
- Thermal stresses do not affect shear
# Stress Concentration
- Stress distribution will be uniform far from all applied loads and geometry changes
- $\sigma_{\text{max}}$: maximum observable stress at any point
- $\sigma_{\text{nom}}$: the average stress at the smallest cross-section
- $K$: a dimensionless number relating the two stresses above $K\equiv\left( \frac{\sigma_{\text{max}}}{\sigma_{\text{nom}}} \right)$
- $K$ depends only on geometry
- Ductile material $f_{s}=\frac{|\sigma_{\text{nom}}|}{\sigma_{Y}}$
- Brittle material $f_{s}=\frac{|\sigma_{\text{max}}|}{\sigma_{UT}}$$f_{s}=\frac{|\sigma_{\text{max}}|}{\sigma_{UC}}$
- Failure when the factor of safety is less than one
# Torsion
## Part 1
- Assume isotropic material
- the cross sections rotate but remain planar in the cylinder
- $L$ is the length of the shaft
- $r$ is an arbitrary radius
- $T$ is the applied torque
- $\phi$ is the angle by which one end of the shaft rotates
- $\gamma$ is the shear strain experienced at some radius $r$
- $L\gamma_{surf}=r_{surf}\phi$ or for an arbitrary radius, $L\gamma=r\phi$
- Using Hooke's law for shear, $\tau=G\gamma=\frac{Gr}{L}\phi$
- $\phi=\frac{TL}{GJ}$, this is for cylinders since $J$ is the polar moment of area
- $J\equiv \begin{cases} \frac{\pi}{2}r_{surf}^{4} \quad \text{Solid shaft} \\ \frac{\pi}{2} (r_{surf}^{4}-r_{in}^{4})\quad \text{Hollow shaft any thickness }\\ 2\pi tr_{surf}^{3}\quad \text{thickness} \frac{t}{r_{surf}}<0.01 \end{cases}$ 
- $\frac{\tau}{r}=\frac{T}{J}=\frac{G}{L}\phi$
- $\gamma(r)=\frac{\tau(r)}{G}$
- $\delta=\frac{FL}{AE}$
- $\phi=\frac{TL}{JG}$
## Part 2
- $F_{||}=\frac{T}{r}$
- $\frac{T_{1}}{r_{1}}=\frac{T_{2}}{r_{2}}$
- $\delta_{1}=-\delta_{2}\Rightarrow r_{1}\phi_{1}=-r_{2}\phi_{2}$
- In cases of various properties and loading remember to make cuts
# Shear And Bending Moment diagrams
- $V(z)$ is the shear force at $z$
- $M(z)$ is the bending moment at $z$
- Positive shear pulls the right side down
- Positive moment turns region into a smile
- Let $w(z)$ be a distributed force then $V(z)=\int_{0}^{z}w_{\text{upward} }(z)\,dz+\sum_{0}^{z}F_{\text{upward}}(z)$ and $M(z)=\int_{0}^{z}V(z)dz+\sum_{0}^{z}T_{\text{cw}}(z)$
# Pure Bending
- For some loaded beam, a point $z$ is said to be in a state of pure bending if $V(z)=0$ and $M(z)\neq0$
- Thee neutral layer is the one layer in the beam that has not changed length
- $z$ horizontal coordinate along beam
- $\rho$ radius of curvature, positive for smile deformation
- $y$ distance above the neutral layer
- $y^*$ co-ordinate system parallel to $y$ but not necessarily having $0$ at neutral axis 
- $y^{*}_{\text{NA}}$ location of the neutral axis  in the $y^*$ coordinate system
- $\varepsilon_{z}=-\frac{y}{\rho}$
- $\sigma_{z}=E \varepsilon_{z}=-E \cdot \frac{y}{\rho}$
- $I_x$ second moment of inertia which in solid mechanics represents how strongly the cross section resists bending about the x axis
- $\frac{\sigma_{z}}{-y}=\frac{M_{x}}{I_{x}}=\frac{E}{\rho}$
- The peak bending stress occurs at the maximum $|y|$
- For composite shapes:
	- $y^{*}_{\text{NA}}=\frac{1}{A_{\text{total}}}\sum_{i=1}^{n_{\text{components}}}y^{*}_{\text{NA},i}A_{i}$
	- $I_{x}=\sum_{i=1}^{n_{\text{components}}}I_{x,i}+\sum_{i=1}^{n_{\text{components}}}A_{i}(y_{\text{NA, }i}^{*}-y^{*}_{\text{NA}})^{2}$
# Working With Moments of Area
- In the $xy$ plane,
	- $I_{x}=\int_{A_{\perp}}y^2dA$
	- $I_{y}=\int_{A_{\perp}}x^2dA$
	- $J=I_{x}+I_{y}$
- Material father from the axis resist bending/torsion more strongly
# Bending of Composite Beams
 - Increasing $E$ at some point is the same as increasing local width
 - To solve these questions we choose a reference material and then we adjust the axis parallel to the neutral axis to $L_{\text{new}}=L\cdot \frac{E}{E_{\text{ref}}}$
# Plane Stress Transformation
- Plane Stress: a system is in a state of plane stress if there is at least one coordinate system for which $\sigma_{z}=\tau_{zx}=\tau_{zy}=0$
- Use Mohrs circle for the transformations
- Remember to double the angle when moving to mohrs circle
# Principle Stresses
- At each point in an arbitrarily loaded material there exists at least one principle coordinate system where all shear stresses are zero
- The three normal stresses are called the principle stresses
- The standard notation is $\sigma_{1}\geq\sigma_{2}\geq\sigma_{3}$
- When all the principle stress are equal the 3D Mohrs circle is a dot and it is in hydrostatic stress
# Maximum Shear & Tresca Criterion
- If the shear on any plane gets too large that plain will fail
- Consider a Mohrs circle, $f_{s}^{\text{Tresca}}=\frac{\sigma_{\frac{Y}{2}}}{\tau_{\text{max}}}$
- The plane with the highest shear stress is called the critical plane which is the plane that is closest to failing
# Von Mises and Mohr Criteria
- $\frac{1}{2}[(\sigma_{1}-\sigma_{2})^{2}+(\sigma_{2}-\sigma_{3})^{2}+(\sigma_{1}-\sigma_{3})^{2}]=\left( \frac{\sigma_{Y}}{f_{s}^{\text{vM}}} \right)^2$ using the principle stresses
- The von Mises equivalent stress is a single value that quantifies how intense the loading is overall and is also applicable to isotropic ductile materials
- The von Mises is more accurate than the Tresca model but the Tresca model is still acceptable since it is conservative
- $f_{s}^{\text{vM}}\geq f_{s}^{\text{Tresca}}$, $f_{s}^{\text{vM}}\leq\left( \frac{2}{\sqrt{ 3 }} \right) f_{s}^{\text{Tresca}}$ the maximum discrepancy is quite small
- The Mohr criterion is for brittle materials
- $\frac{\sigma_{\text{max}}}{\sigma_{UT}}-\frac{\sigma_{\text{min}}}{|\sigma_{UC}|}=\frac{1}{f_{S}^{\text{Mohr}}}$ this is a reasonable model for isotropic brittle materials
- **Selecting a Criterion**
	- Brittle $\longleftrightarrow$ Mohr
	- Ductile, Simple & Conservative $\longleftrightarrow$ Tresca
	- Ductile, Complex & Precise $\longleftrightarrow$ Von Mises
# Thin Walled Pressure Vessels
- $P_{\text{gauge}}=P_{\text{abs}}-P_{\text{atm}}$
- $\sigma_{\text{gauge}}=\sigma_{\text{abs}}-\sigma_{\text{atm}}$
- For fluids, $\sigma>P_{\text{atm}}\implies$ negative absolute pressure; gases fail (pull apart), liquids metastable
- $\sigma<P_{\text{atm}}\implies$ positive absolute pressure; stable
- $\tau \neq 0$ failure(flowing)
- Mohrs dot is the only Mohrs circle that can fir inside the failure envelope
- In a pressure vessel, $P$ is the Gauge pressure inside the tank $P=P_{\text{inside}}-P_{\text{outside}}$
- If the tank is pressurized from the outside we have $P<0$
- The pressure in a liquid increases with depth according to $P=\rho gh$, this formula does not apply to gases
- **Thin walled** $\implies \frac{t}{r}\leq 0.1$
- Use inner radius
- $\sigma_{ax}$: the axial stress in a cylinder
- $\sigma_{\theta}^{cyl}$: the "circumferential" or "hoop" stress in a cylinder
- $\sigma_{\theta}^{sph}$: the "circumferential" or "hoop" stress in a sphere
- $\sigma_{\theta}^{cyl}=\frac{Pr}{t}$
- $\sigma_{ax}=\frac{Pr}{2t\left( 1+\frac{t}{2r} \right)}\approx \frac{Pr}{2t}$
- $\sigma_{\theta}^{sph}=\sigma_{ax}$
- For a cylinder $\varepsilon_{V}\approx 2\varepsilon_{\theta}+\varepsilon_{ax}$
# Strain Transformation & Rosettes
- $\varepsilon_{x}'=\varepsilon_{x}\cos ^{2}\theta+\varepsilon_{y}\sin ^{2}\theta+\gamma_{xy}\sin \theta \cos \theta$ where $\theta$ is the angle to the $x'$ direction from the reference