# note
## chapter 3
### Mason's rule
$$ G=\frac{1}{\Delta}\sum\limits_{k=1}^NP_K\Delta_k $$
...
### time-domain specification
![1](Picture%201.png){:height="50%" width="50%"}
> if the system's overshoot is zero, which means it will cost infinite time to get $c(t_{\infty})$, so $ t_r=c^{-1}(0.9)-c^{-1}(0.1) $

second-order system
standard form:

$ \Phi (s)= \frac{ \omega_n^2}{s^2+2\xi \omega_n^2+\omega_n^2} $
>$\xi\geq0\qquad \omega_n>0 $

* $ \omega_n $- natural frequency
* $ \xi $- damping ratio

$ s_{1,2}=- \xi \omega_n \pm \omega_n \sqrt{\xi^2-1} $
a unit step input:$c(t)=1-\frac{e^{-\xi\omega_nt}}{\sqrt{1-\xi^2}}\sin(\omega_d t+\theta) $
![2](Picture%202.png){:height="50%" width="50%"}
* $t_p=\frac{\pi}{\omega_n\sqrt{1-\xi^2}}=\frac{\pi}{\omega_d}$ $~~~$ by$ \frac{dc(t)}{dt}|_{t=t_p}=0 $
* $\sigma_p=e^{-\frac{\xi\pi}{\sqrt{1-\xi^2}}}\times100 \%$$~~~$by$c(t_p)-1$
* $t_s=\frac{-\ln(0.05)}{\xi\omega_n}\approx\frac{3.5}{\xi\omega_n},\qquad \Delta=0.05$
* $ t_s\approx\frac{4.4}{\xi\omega_n},\qquad \Delta=0.02 $
* $ t_r=\frac{\pi-\theta}{\omega_d}    \qquad \theta=\cos^{-1}(\xi)$

##### critical damping system
$\xi=1$,$c(s)=\frac{1}{s}-\frac{\omega_n}{(s+\omega_n)^2}-\frac{1}{s+\omega_n}\Rightarrow c(t)=1-e^{-\omega_n t}(1+\omega_n t) $

![3](Picture%203.png){:height="50%" width="50%" }

#### high-order system
Dominant Pole:  The closed-loop poles closest to the imaginary axis dominate the dynamic response.
>if$|\text{Re}(p_1)|>5|\text{Re}(p_2)| $,then the first pole can be neglected

Dipole: Zeros and poles in the same location or quite close with each other affect the dynamic response very little.

##### amplitude&time scaling
amplitude scaling
$$ x=c_xx $$
time scaling
$$ \dot{x}=\frac{ddx}{t}=\omega_n\frac{dx}{d(t\omega_n)} $$
##### the effect of zeros
Add one zero at RHP could cause a downshoot,otherwise it will increase overshoot.
##### stability
Routh criterion
Routh table
$$ D(s)=a_5s^5+a_4s^4+...+a_0 $$
| $s^5$| $a_5$| $a_3$ |$a_1$|
|----------|----------|--------|-------|
|  $s^4$ |   $a_4$  |  $a_2$  |$a_0$|
|   $s^3$  |   $A_1$ |   $A_2$  |
|$s^2$|$B_1$|$B_2$
|$s$|$C_1$|
|$s^0$|$D_1$|

>remark 1:
if  $K_1=0$ , transform $ 0$ to $\varepsilon$
remark 2 :
if the cofficients in one row is zero, derivate last polynomial to get new polynomial.

## chapter 4
sensitivity:$$\frac {\delta y}{y}=S \frac{\delta x}{x}  $$
>$$ \delta y=\frac{dy}{dx}\delta x $$
### system type
determine stability
* check poles
* Routh
* steady-state error $e_{ss}$

$$ E(s)=R(s)-Y(s)=\frac{1}{1+G(s)H(S)}R(s) $$
simplify
![alt text](image-1.png)
system type
* have no pole at origin ->type-0
* have one pole at origin ->type-1
* etc.

#### error coefficients
1. step input:$e_{ss}=\lim\limits_{s\rightarrow 0}sE(s)= \frac{1}{1+\lim\limits_{s\rightarrow 0}H(s)G(s)}$,$e_{ss}=\frac{1}{1+k_p}(\text{type-0})||0(\text{otherwise})$
2. ramp input: $e_{ss}=\lim\limits_{s\rightarrow 0}\frac{1}{sG(s)H(s)} $,$k_v=\lim\limits_{s\rightarrow 0}sH(s)G(s) $
3. acceleration input:  $e_{ss}=\lim\limits_{s\rightarrow 0}\frac{1}{s^2G(s)H(s)} $ 
#### PID
**P**(Proportional): decrease rising time, but if K is too large, the system will be unstable.
**I**(Integral): decrease steady-state error, but if K is too large, it may increase overshoot.
**D**(derivate): reduce overshoot, make the system more stable. But it slows the transist response, and make system sensitive to noise.

## chapter 5

fundamental formation 
$$ 1+K L(s)=0 $$
six rules to plot root locus
* starting point and end point
* on the real axis
* asymptotes 
* angle of departure and angle of arrival
* crossing imaginary axis
* muti-point
***
$$G(s)H(s)=\frac{K\prod\limits^m (s-z_i)}{\prod\limits^n (s-p_i)}$$
asymptotes:
$$\varphi=\frac{2k-1}{n-m}\pi$$
$$a=\frac{\sum p_i-\sum z_i}{n-m} $$
the rule is to determine how to draw root locus without the help of computer