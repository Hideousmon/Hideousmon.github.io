---
layout: post
title:  "Wavelength- and Bandwidth-tubable Microring"
categories: NanoPhotonic
tags: Microring
author: Zhenyu ZHAO
---

* content
{:toc}




<center>    <img style="border-radius: 0.3125em;    box-shadow: 0 2px 4px 0 rgba(34,36,38,.12),0 2px 10px 0 rgba(34,36,38,.08);"     src="https://github.com/Hideousmon/Hideousmon.github.io/raw/master/_img/posts/Wavelength-_and_Bandwidth-_tunable_Microring.png"> </center>

### Basic Equations for the coupling

<center> <img src="http://latex.codecogs.com/gif.latex?E_{o11} = t_1 * E_{i11} + k_1*E_{i12}"/>  <p align="right"> (1) </p>  </center>

<center><img src="http://latex.codecogs.com/gif.latex? E_{o12}=t_1^**E_{i12}+k_1^* *E_{i11}"/> <p align="right"> (2) </p> </center>

<center><img src="http://latex.codecogs.com/gif.latex?E_{o21} = t_2 * E_{i21} + k_2*E_{i22}"/> <p align="right"> (3) </p> </center>

<center><img src="http://latex.codecogs.com/gif.latex?E_{o22}=t_2^**E_{i22}+k_2^* *E_{i21}"/> <p align="right"> (4) </p> </center>

<center><img src="http://latex.codecogs.com/gif.latex?E_{o31} = t_3 * E_{i31} + k_3*E_{i32}"/> <p align="right"> (5) </p> </center>

<center><img src="http://latex.codecogs.com/gif.latex?E_{o32}=t_3^**E_{i32}+k_3^* *E_{i31}"/> <p align="right"> (6) </p> </center>

<center><img src="http://latex.codecogs.com/gif.latex?E_{o41} = t_4 * E_{i41} + k_4*E_{i42}"/> <p align="right"> (7) </p> </center>

<center><img src="http://latex.codecogs.com/gif.latex?E_{o42}=t_4^**E_{i42}+k_4^* *E_{i41}"/> <p align="right"> (8) </p> </center>

### Transition Equations

<center><img src="http://latex.codecogs.com/gif.latex? E_{i22} = E_{o12}*e^ {i\theta_1} "/> <p align="right"> (9) </p> </center>

<center><img src="http://latex.codecogs.com/gif.latex? E_{i32}=E_{o22}*e^{i\theta_2} "/> <p align="right"> (10) </p> </center>

<center><img src="http://latex.codecogs.com/gif.latex? E_{i42}=E_{o32}*e^{i\theta_3} "/> <p align="right"> (11) </p> </center>

<center><img src="http://latex.codecogs.com/gif.latex? E_{i12} = E_{o42}*e^{i\theta_4} "/> <p align="right"> (12) </p> </center>

<center><img src="http://latex.codecogs.com/gif.latex? E_{i21} = E_{o11}*e^{i\phi_1} "/> <p align="right"> (13) </p> </center>

<center><img src="http://latex.codecogs.com/gif.latex? E_{i41}=E_{o31}*e^{i\phi_2} "/> <p align="right"> (14) </p> </center>


### Calculate Ei12

Assuming ：
<center><img src="http://latex.codecogs.com/gif.latex? E_{i31} = 0"/> </center>

#### 1. Combine (2)(4)(9)(13)

<center><img src="http://latex.codecogs.com/gif.latex? 
E_{o22} = t_2^**(E_{o12}*e^ {i\theta_1})+k_2^* *(E_{o11}*e^{i\phi_1})\\
= t_2^**((t_1^**E_{i12}+k_1^* *E_{i11})*e^ {i\theta_1})+k_2^* *((t_1 * E_{i11} + k_1*E_{i12})*e^{i\phi_1}) 
"/> <p align="right"> (15) </p> </center>




#### 2. Combine (6)(10)(15)
<center><img src="http://latex.codecogs.com/gif.latex? E_{o32}=k_3^* *((t_2^**((t_1^**E_{i12}+k_1^* *E_{i11})*e^ {i\theta_1})\\+ k_2^* *((t_1 * E_{i11} + k_1*E_{i12})*e^{i\phi_1}))*e^{i\theta_2}) "/> <p align="right"> (16) </p> </center>

#### 3. Combine (5)(10)(15)
<center><img src="http://latex.codecogs.com/gif.latex? E_{o31} =  k_3*((t_2^**((t_1^**E_{i12}+k_1^* *E_{i11})*e^ {i\theta_1})\\+  k_2^* *((t_1 * E_{i11} + k_1*E_{i12})*e^{i\phi_1}))*e^{i\theta_2})"/> <p align="right"> (17) </p> </center>


#### 4. Combine (8)(11)(14)(16)(17)
<center><img src="http://latex.codecogs.com/gif.latex?E_{o42} = t_4^**((k_3^* *((t_2^**((t_1^**E_{i12}+k_1^* *E_{i11})*e^ {i\theta_1})\\+k_2^* *((t_1 * E_{i11} + k_1*E_{i12})*e^{i\phi_1}))*e^{i\theta_2}))*e^{i\theta_3})\\+k_4^* *((k_3*((t_2^**((t_1^**E_{i12}+k_1^* *E_{i11})*e^ {i\theta_1})\\+k_2^* *((t_1 * E_{i11} + k_1*E_{i12})*e^{i\phi_1}))*e^{i\theta_2}))*e^{i\phi_2})"/> <p align="right"> (18) </p> </center>


#### 5. Combine (12)(18)
<center><img src="http://latex.codecogs.com/gif.latex? E_{i12} = (t_4^**((k_3^* *((t_2^**((t_1^**E_{i12}+k_1^* *E_{i11})*e^ {i\theta_1})\\+k_2^* *((t_1 * E_{i11} + k_1*E_{i12})*e^{i\phi_1}))*e^{i\theta_2}))*e^{i\theta_3})\\+k_4^* *((k_3*((t_2^**((t_1^**E_{i12}+k_1^* *E_{i11})*e^ {i\theta_1})\\+k_2^* *((t_1 * E_{i11} + k_1*E_{i12})*e^{i\phi_1}))*e^{i\theta_2}))*e^{i\phi_2}))*e^{i\theta_4} "/> <p align="right"> (19) </p> </center>


### Calculate Eo11​ with Ei11

#### 1. Solve Equation(19)
<center><img src="http://latex.codecogs.com/gif.latex? E_{i12} = t_4^**k_3^* *t_2^**t_1^**E_{i12}*e^ {i\theta_1}*e^{i\theta_3}*e^{i\theta_4}\\
+t_4^**k_3^* *t_2^**k_1^* *E_{i11}*e^ {i\theta_1}*e^{i\theta_3}*e^{i\theta_4} \\
+t_4^**k_3^* *k_2^* *t_1 * E_{i11}*e^{i\phi_1}*e^{i\theta_2}*e^{i\theta_3}*e^{i\theta_4} \\
+t_4^**k_3^* *k_2^* *k_1*E_{i12}*e^{i\phi_1}*e^{i\theta_2}*e^{i\theta_3}*e^{i\theta_4}\\
+t_4^**k_4^* *k_3*t_2^**t_1^**E_{i12}*e^ {i\theta_1}*e^{i\theta_2}*e^{i\phi_2}*e^{i\theta_4}\\
+t_4^**k_4^* *k_3*k_1^* *E_{i11}*e^ {i\theta_1}*e^{i\theta_2}*e^{i\phi_2}*e^{i\theta_4}\\
+t_4^**k_4^* *k_3*t_2^**k_2^* *t_1 * E_{i11}*e^{i\phi_1}*e^{i\theta_2}*e^{i\phi_2}*e^{i\theta_4} \\
+t_4^**k_4^* *k_3*t_2^**k_2^* *k_1*E_{i12}*e^{i\phi_1}*e^{i\theta_2}*e^{i\phi_2}*e^{i\theta_4} "/> <p align="right"> (20) </p> </center>

<center><img src="http://latex.codecogs.com/gif.latex? (1-t_4^**k_3^* *t_2^**t_1^**e^ {i\theta_1}*e^{i\theta_3}*e^{i\theta_4} \\
- t_4^**k_3^* *k_2^* *k_1*e^{i\phi_1}*e^{i\theta_2}*e^{i\theta_3}*e^{i\theta_4} \\
- t_4^**k_4^* *k_3*t_2^**t_1^**e^ {i\theta_1}*e^{i\theta_2}*e^{i\phi_2}*e^{i\theta_4}\\
- t_4^**k_4^* *k_3*t_2^**k_2^* *k_1*e^{i\phi_1}*e^{i\theta_2}*e^{i\phi_2}*e^{i\theta_4})*E_{i12} \\
= (t_4^**k_3^* *t_2^**k_1^* *e^ {i\theta_1}*e^{i\theta_3}*e^{i\theta_4} \\
+ t_4^**k_3^* *k_2^* *t_1 *e^{i\phi_1}*e^{i\theta_2}*e^{i\theta_3}*e^{i\theta_4} \\
+ t_4^**k_4^* *k_3*k_1^* *e^ {i\theta_1}*e^{i\theta_2}*e^{i\phi_2}*e^{i\theta_4}\\
+ t_4^**k_4^* *k_3*t_2^**k_2^* *t_1 *e^{i\phi_1}*e^{i\theta_2}*e^{i\phi_2}*e^{i\theta_4})*E_{i11}"/> <p align="right"> (21) </p> </center>



<center><img src="http://latex.codecogs.com/gif.latex? \frac{E_{i12}}{E_{i11}} = \frac{t_4^**k_3^* *t_2^**k_1^* *e^ {i\theta_1}*e^{i\theta_3}*e^{i\theta_4} 
+ t_4^**k_3^* *k_2^* *t_1 *e^{i\phi_1}*e^{i\theta_2}*e^{i\theta_3}*e^{i\theta_4} \\
+ t_4^**k_4^* *k_3*k_1^* *e^ {i\theta_1}*e^{i\theta_2}*e^{i\phi_2}*e^{i\theta_4}
+ t_4^**k_4^* *k_3*t_2^**k_2^* *t_1 *e^{i\phi_1}*e^{i\theta_2}*e^{i\phi_2}*e^{i\theta_4}}{1-t_4^**k_3^* *t_2^**t_1^**e^ {i\theta_1}*e^{i\theta_3}*e^{i\theta_4} 
- t_4^**k_3^* *k_2^* *k_1*e^{i\phi_1}*e^{i\theta_2}*e^{i\theta_3}*e^{i\theta_4} \\
- t_4^**k_4^* *k_3*t_2^**t_1^**e^ {i\theta_1}*e^{i\theta_2}*e^{i\phi_2}*e^{i\theta_4}
- t_4^**k_4^* *k_3*t_2^**k_2^* *k_1*e^{i\phi_1}*e^{i\theta_2}*e^{i\phi_2}*e^{i\theta_4}}"/> <p align="right"> (22) </p> </center>


### Calculate Eo21 with ​Ei11

#### 1. Combine Equation(1)(2)(3)(9)(13)
<center><img src="http://latex.codecogs.com/gif.latex? E_{o21} = (t_2 * t_1 *e^{i\phi_1}+k_2*k_1^* *e^ {i\theta_1})*E_{i11} + (t_2 * k_1*e^{i\phi_1} + k_2*t_1^**e^ {i\theta_1})*E_{i12}"/> <p align="right"> (23) </p> </center>


#### 2. Combine Equation(22)(23)
<center><img src="http://latex.codecogs.com/gif.latex? E_{o21} = (t_2 * t_1 *e^{i\phi_1}+k_2*k_1^* *e^ {i\theta_1})*E_{i11} + (t_2 * k_1*e^{i\phi_1} + k_2*t_1^**e^ {i\theta_1})*\frac{t_4^**k_3^* *t_2^**k_1^* *e^ {i\theta_1}*e^{i\theta_3}*e^{i\theta_4} 
+ t_4^**k_3^* *k_2^* *t_1 *e^{i\phi_1}*e^{i\theta_2}*e^{i\theta_3}*e^{i\theta_4} \\
+ t_4^**k_4^* *k_3*k_1^* *e^ {i\theta_1}*e^{i\theta_2}*e^{i\phi_2}*e^{i\theta_4}
+ t_4^**k_4^* *k_3*t_2^**k_2^* *t_1 *e^{i\phi_1}*e^{i\theta_2}*e^{i\phi_2}*e^{i\theta_4}}{1-t_4^**k_3^* *t_2^**t_1^**e^ {i\theta_1}*e^{i\theta_3}*e^{i\theta_4} 
- t_4^**k_3^* *k_2^* *k_1*e^{i\phi_1}*e^{i\theta_2}*e^{i\theta_3}*e^{i\theta_4} \\
- t_4^**k_4^* *k_3*t_2^**t_1^**e^ {i\theta_1}*e^{i\theta_2}*e^{i\phi_2}*e^{i\theta_4}
- t_4^**k_4^* *k_3*t_2^**k_2^* *k_1*e^{i\phi_1}*e^{i\theta_2}*e^{i\phi_2}*e^{i\theta_4}}*E_{i11}"/> </center>






### Calculate Eo41 with Ei11

#### 1.Combine Equation(7)(11)(14)(16)(17)(19)
<center><img src="http://latex.codecogs.com/gif.latex? E_{o41} =  t_4 *k_3*t_2^**t_1^**E_{i12}*e^ {i\theta_1}*e^{i\theta_2}*e^{i\phi_2}
+t_4 *k_3*t_2^**k_1^* *E_{i11}*e^ {i\theta_1}*e^{i\theta_2}*e^{i\phi_2}\\
+t_4 *k_3*k_2^* *t_1 * E_{i11}*e^{i\phi_1}*e^{i\theta_2}*e^{i\phi_2} 
+t_4 *k_3*k_2^* *k_1*E_{i12}*e^{i\phi_1}*e^{i\theta_2}*e^{i\phi_2} \\
+k_4*k_3^* *t_2^**t_1^**E_{i12}*e^ {i\theta_1}*e^{i\theta_2}*e^{i\theta_3}
+k_4*k_3^* *t_2^**k_1^* *E_{i11}*e^ {i\theta_1}*e^{i\theta_2}*e^{i\theta_3}\\
+k_4*k_3^* *k_2^* *t_1 * E_{i11}*e^{i\phi_1}*e^{i\theta_2}*e^{i\theta_3} 
+k_4*k_3^* *k_2^* *k_1*E_{i12}*e^{i\phi_1}*e^{i\theta_2}*e^{i\theta_3} "/> <p align="right"> (24) </p> </center>

<center><img src="http://latex.codecogs.com/gif.latex?E_{o41} = (t_4 *k_3*t_2^**k_1^* *e^ {i\theta_1}*e^{i\theta_2}*e^{i\phi_2} 
+ t_4 *k_3*k_2^* *t_1 *e^{i\phi_1}*e^{i\theta_2}*e^{i\phi_2} \\
+ k_4*k_3^* *t_2^**k_1^* *e^ {i\theta_1}*e^{i\theta_2}*e^{i\theta_3} 
+ k_4*k_3^* *k_2^* *t_1 *e^{i\phi_1}*e^{i\theta_2}*e^{i\theta_3})*E_{i11} \\
+ (t_4 *k_3*t_2^**t_1^**e^ {i\theta_1}*e^{i\theta_2}*e^{i\phi_2}
+ t_4 *k_3*k_2^* *k_1*e^{i\phi_1}*e^{i\theta_2}*e^{i\phi_2}\\
+ k_4*k_3^* *t_2^**t_1^**e^ {i\theta_1}*e^{i\theta_2}*e^{i\theta_3}
+ k_4*k_3^* *k_2^* *k_1*e^{i\phi_1}*e^{i\theta_2}*e^{i\theta_3})*E_{i12}"/> <p align="right"> (25) </p> </center>


#### 2. Combine Equation(22)(24)
<center><img src="http://latex.codecogs.com/gif.latex? E_{o41} = (t_4 *k_3*t_2^**k_1^* *e^ {i\theta_1}*e^{i\theta_2}*e^{i\phi_2} 
+ t_4 *k_3*k_2^* *t_1 *e^{i\phi_1}*e^{i\theta_2}*e^{i\phi_2} \\
+ k_4*k_3^* *t_2^**k_1^* *e^ {i\theta_1}*e^{i\theta_2}*e^{i\theta_3} 
+ k_4*k_3^* *k_2^* *t_1 *e^{i\phi_1}*e^{i\theta_2}*e^{i\theta_3})*E_{i11} \\
+ (t_4 *k_3*t_2^**t_1^**e^ {i\theta_1}*e^{i\theta_2}*e^{i\phi_2}
+ t_4 *k_3*k_2^* *k_1*e^{i\phi_1}*e^{i\theta_2}*e^{i\phi_2}\\
+ k_4*k_3^* *t_2^**t_1^**e^ {i\theta_1}*e^{i\theta_2}*e^{i\theta_3}
+ k_4*k_3^* *k_2^* *k_1*e^{i\phi_1}*e^{i\theta_2}*e^{i\theta_3}) \\
"/> </center>
<center><img src="http://latex.codecogs.com/gif.latex? 
*\frac{t_4^**k_3^* *t_2^**k_1^* *e^ {i\theta_1}*e^{i\theta_3}*e^{i\theta_4} 
+ t_4^**k_3^* *k_2^* *t_1 *e^{i\phi_1}*e^{i\theta_2}*e^{i\theta_3}*e^{i\theta_4} \\
+ t_4^**k_4^* *k_3*k_1^* *e^ {i\theta_1}*e^{i\theta_2}*e^{i\phi_2}*e^{i\theta_4}
+ t_4^**k_4^* *k_3*t_2^**k_2^* *t_1 *e^{i\phi_1}*e^{i\theta_2}*e^{i\phi_2}*e^{i\theta_4}}{1-t_4^**k_3^* *t_2^**t_1^**e^ {i\theta_1}*e^{i\theta_3}*e^{i\theta_4} 
- t_4^**k_3^* *k_2^* *k_1*e^{i\phi_1}*e^{i\theta_2}*e^{i\theta_3}*e^{i\theta_4} \\
- t_4^**k_4^* *k_3*t_2^**t_1^**e^ {i\theta_1}*e^{i\theta_2}*e^{i\phi_2}*e^{i\theta_4}
- t_4^**k_4^* *k_3*t_2^**k_2^* *k_1*e^{i\phi_1}*e^{i\theta_2}*e^{i\phi_2}*e^{i\theta_4}}*E_{i11}"/></center>




