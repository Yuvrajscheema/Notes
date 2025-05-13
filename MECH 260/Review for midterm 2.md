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
 - After doing this, to get stresses we must use $\sigma_{\text{actual}}=\sigma \cdot \frac{E}{E_{ref}}$