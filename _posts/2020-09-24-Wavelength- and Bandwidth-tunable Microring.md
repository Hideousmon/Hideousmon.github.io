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

<center><img src="http://latex.codecogs.com/gif.latex?E_{o11} = t_1 * E_{i11} + k_1*E_{i12}"/> (1) </center>

<center><img src="http://latex.codecogs.com/gif.latex? E_{o12}=t_1^**E_{i12}+k_1^* *E_{i11}"/> (2) </center>

<center><img src="http://latex.codecogs.com/gif.latex?E_{o21} = t_2 * E_{i21} + k_2*E_{i22}"/> (3) </center>

<center><img src="http://latex.codecogs.com/gif.latex?E_{o22}=t_2^**E_{i22}+k_2^* *E_{i21}"/> (4) </center>

<center><img src="http://latex.codecogs.com/gif.latex?E_{o31} = t_3 * E_{i31} + k_3*E_{i32}"/> (5) </center>

<center><img src="http://latex.codecogs.com/gif.latex?E_{o32}=t_3^**E_{i32}+k_3^* *E_{i31}"/> (6) </center>

<center><img src="http://latex.codecogs.com/gif.latex?E_{o41} = t_4 * E_{i41} + k_4*E_{i42}"/> (7) </center>

<center><img src="http://latex.codecogs.com/gif.latex?E_{o42}=t_4^**E_{i42}+k_4^* *E_{i41}"/> (8) </center>

### Transition Equations

<center><img src="http://latex.codecogs.com/gif.latex? E_{i22} = E_{o12}*e^ {i\theta_1} "/> (9) </center>

<center><img src="http://latex.codecogs.com/gif.latex? E_{i32}=E_{o22}*e^{i\theta_2} "/> (10) </center>

<center><img src="http://latex.codecogs.com/gif.latex? E_{i42}=E_{o32}*e^{i\theta_3} "/> (11) </center>

<center><img src="http://latex.codecogs.com/gif.latex? E_{i12} = E_{o42}*e^{i\theta_4} "/> (12) </center>

<center><img src="http://latex.codecogs.com/gif.latex? E_{i21} = E_{o11}*e^{i\phi_1} "/> (13) </center>

<center><img src="http://latex.codecogs.com/gif.latex? E_{i41}=E_{o31}*e^{i\phi_2} "/> (14) </center>


### Calculate $E_{i12}$

Assuming ：
<center><img src="http://latex.codecogs.com/gif.latex? E_{i31} = 0"/> </center>

#### 1. Combine (2)(4)(9)(13)

<center><img src="http://latex.codecogs.com/gif.latex? 
E_{o22} = t_2^**(E_{o12}*e^ {i\theta_1})+k_2^* *(E_{o11}*e^{i\phi_1})\\
= t_2^**((t_1^**E_{i12}+k_1^* *E_{i11})*e^ {i\theta_1})+k_2^* *((t_1 * E_{i11} + k_1*E_{i12})*e^{i\phi_1}) 
"/> (15) </center>



#### 2. Combine (6)(10)(15)
<center><img src="http://latex.codecogs.com/gif.latex? E_{o32}=k_3^* *((t_2^**((t_1^**E_{i12}+k_1^* *E_{i11})*e^ {i\theta_1})\\+ k_2^* *((t_1 * E_{i11} + k_1*E_{i12})*e^{i\phi_1}))*e^{i\theta_2}) "/> (16) </center>

#### 3. Combine (5)(10)(15)
<center><img src="http://latex.codecogs.com/gif.latex? E_{o31} =  k_3*((t_2^**((t_1^**E_{i12}+k_1^* *E_{i11})*e^ {i\theta_1})\\+  k_2^* *((t_1 * E_{i11} + k_1*E_{i12})*e^{i\phi_1}))*e^{i\theta_2})"/> (17) </center>


#### 4. Combine (8)(11)(14)(16)(17)
<center><img src="http://latex.codecogs.com/gif.latex?E_{o42} = t_4^**((k_3^* *((t_2^**((t_1^**E_{i12}+k_1^* *E_{i11})*e^ {i\theta_1})\\+k_2^* *((t_1 * E_{i11} + k_1*E_{i12})*e^{i\phi_1}))*e^{i\theta_2}))*e^{i\theta_3})\\+k_4^* *((k_3*((t_2^**((t_1^**E_{i12}+k_1^* *E_{i11})*e^ {i\theta_1})\\+k_2^* *((t_1 * E_{i11} + k_1*E_{i12})*e^{i\phi_1}))*e^{i\theta_2}))*e^{i\phi_2})"/> (18) </center>


#### 5. Combine (12)(18)
<center><img src="http://latex.codecogs.com/gif.latex? E_{i12} = (t_4^**((k_3^* *((t_2^**((t_1^**E_{i12}+k_1^* *E_{i11})*e^ {i\theta_1})\\+k_2^* *((t_1 * E_{i11} + k_1*E_{i12})*e^{i\phi_1}))*e^{i\theta_2}))*e^{i\theta_3})\\+k_4^* *((k_3*((t_2^**((t_1^**E_{i12}+k_1^* *E_{i11})*e^ {i\theta_1})\\+k_2^* *((t_1 * E_{i11} + k_1*E_{i12})*e^{i\phi_1}))*e^{i\theta_2}))*e^{i\phi_2}))*e^{i\theta_4} "/> (19) </center>


### Calculate $E_{o11}$ with $E_{i11}$

#### 1. Solve Equation(19)
<center><img src="http://latex.codecogs.com/gif.latex? E_{i12} = t_4^**k_3^* *t_2^**t_1^**E_{i12}*e^ {i\theta_1}*e^{i\theta_3}*e^{i\theta_4}\\
+t_4^**k_3^* *t_2^**k_1^* *E_{i11}*e^ {i\theta_1}*e^{i\theta_3}*e^{i\theta_4} \\
+t_4^**k_3^* *k_2^* *t_1 * E_{i11}*e^{i\phi_1}*e^{i\theta_2}*e^{i\theta_3}*e^{i\theta_4} \\
+t_4^**k_3^* *k_2^* *k_1*E_{i12}*e^{i\phi_1}*e^{i\theta_2}*e^{i\theta_3}*e^{i\theta_4}\\
+t_4^**k_4^* *k_3*t_2^**t_1^**E_{i12}*e^ {i\theta_1}*e^{i\theta_2}*e^{i\phi_2}*e^{i\theta_4}\\
+t_4^**k_4^* *k_3*k_1^* *E_{i11}*e^ {i\theta_1}*e^{i\theta_2}*e^{i\phi_2}*e^{i\theta_4}\\
+t_4^**k_4^* *k_3*t_2^**k_2^* *t_1 * E_{i11}*e^{i\phi_1}*e^{i\theta_2}*e^{i\phi_2}*e^{i\theta_4} \\
+t_4^**k_4^* *k_3*t_2^**k_2^* *k_1*E_{i12}*e^{i\phi_1}*e^{i\theta_2}*e^{i\phi_2}*e^{i\theta_4} "/> (20) </center>

<center><img src="http://latex.codecogs.com/gif.latex? (1-t_4^**k_3^* *t_2^**t_1^**e^ {i\theta_1}*e^{i\theta_3}*e^{i\theta_4} \\
- t_4^**k_3^* *k_2^* *k_1*e^{i\phi_1}*e^{i\theta_2}*e^{i\theta_3}*e^{i\theta_4} \\
- t_4^**k_4^* *k_3*t_2^**t_1^**e^ {i\theta_1}*e^{i\theta_2}*e^{i\phi_2}*e^{i\theta_4}\\
- t_4^**k_4^* *k_3*t_2^**k_2^* *k_1*e^{i\phi_1}*e^{i\theta_2}*e^{i\phi_2}*e^{i\theta_4})*E_{i12} \\
= (t_4^**k_3^* *t_2^**k_1^* *e^ {i\theta_1}*e^{i\theta_3}*e^{i\theta_4} \\
+ t_4^**k_3^* *k_2^* *t_1 *e^{i\phi_1}*e^{i\theta_2}*e^{i\theta_3}*e^{i\theta_4} \\
+ t_4^**k_4^* *k_3*k_1^* *e^ {i\theta_1}*e^{i\theta_2}*e^{i\phi_2}*e^{i\theta_4}\\
+ t_4^**k_4^* *k_3*t_2^**k_2^* *t_1 *e^{i\phi_1}*e^{i\theta_2}*e^{i\phi_2}*e^{i\theta_4})*E_{i11}"/> (21) </center>


<center><img src="http://latex.codecogs.com/gif.latex? \frac{E_{i12}}{E_{i11}} = \frac{t_4^**k_3^* *t_2^**k_1^* *e^ {i\theta_1}*e^{i\theta_3}*e^{i\theta_4} 
+ t_4^**k_3^* *k_2^* *t_1 *e^{i\phi_1}*e^{i\theta_2}*e^{i\theta_3}*e^{i\theta_4} \\
+ t_4^**k_4^* *k_3*k_1^* *e^ {i\theta_1}*e^{i\theta_2}*e^{i\phi_2}*e^{i\theta_4}
+ t_4^**k_4^* *k_3*t_2^**k_2^* *t_1 *e^{i\phi_1}*e^{i\theta_2}*e^{i\phi_2}*e^{i\theta_4}}{1-t_4^**k_3^* *t_2^**t_1^**e^ {i\theta_1}*e^{i\theta_3}*e^{i\theta_4} 
- t_4^**k_3^* *k_2^* *k_1*e^{i\phi_1}*e^{i\theta_2}*e^{i\theta_3}*e^{i\theta_4} \\
- t_4^**k_4^* *k_3*t_2^**t_1^**e^ {i\theta_1}*e^{i\theta_2}*e^{i\phi_2}*e^{i\theta_4}
- t_4^**k_4^* *k_3*t_2^**k_2^* *k_1*e^{i\phi_1}*e^{i\theta_2}*e^{i\phi_2}*e^{i\theta_4}}"/> (22) </center>

### Calculate $E_{o21}$ with $E_{i11}$

#### 1. Combine Equation(1)(2)(3)(9)(13)
<center><img src="http://latex.codecogs.com/gif.latex? E_{o21} = (t_2 * t_1 *e^{i\phi_1}+k_2*k_1^* *e^ {i\theta_1})*E_{i11} + (t_2 * k_1*e^{i\phi_1} + k_2*t_1^**e^ {i\theta_1})*E_{i12}"/> (23) </center>


#### 2. Combine Equation(22)(23)
<center><img src="http://latex.codecogs.com/gif.latex? E_{o21} = (t_2 * t_1 *e^{i\phi_1}+k_2*k_1^* *e^ {i\theta_1})*E_{i11} + (t_2 * k_1*e^{i\phi_1} + k_2*t_1^**e^ {i\theta_1})*\frac{t_4^**k_3^* *t_2^**k_1^* *e^ {i\theta_1}*e^{i\theta_3}*e^{i\theta_4} 
+ t_4^**k_3^* *k_2^* *t_1 *e^{i\phi_1}*e^{i\theta_2}*e^{i\theta_3}*e^{i\theta_4} \\
+ t_4^**k_4^* *k_3*k_1^* *e^ {i\theta_1}*e^{i\theta_2}*e^{i\phi_2}*e^{i\theta_4}
+ t_4^**k_4^* *k_3*t_2^**k_2^* *t_1 *e^{i\phi_1}*e^{i\theta_2}*e^{i\phi_2}*e^{i\theta_4}}{1-t_4^**k_3^* *t_2^**t_1^**e^ {i\theta_1}*e^{i\theta_3}*e^{i\theta_4} 
- t_4^**k_3^* *k_2^* *k_1*e^{i\phi_1}*e^{i\theta_2}*e^{i\theta_3}*e^{i\theta_4} \\
- t_4^**k_4^* *k_3*t_2^**t_1^**e^ {i\theta_1}*e^{i\theta_2}*e^{i\phi_2}*e^{i\theta_4}
- t_4^**k_4^* *k_3*t_2^**k_2^* *k_1*e^{i\phi_1}*e^{i\theta_2}*e^{i\phi_2}*e^{i\theta_4}}*E_{i11}"/> </center>






### Calculate $E_{o41}$ with $E_{i11}$

#### 1.Combine Equation(7)(11)(14)(16)(17)(19)
<center><img src="http://latex.codecogs.com/gif.latex? E_{o41} =  t_4 *k_3*t_2^**t_1^**E_{i12}*e^ {i\theta_1}*e^{i\theta_2}*e^{i\phi_2}
+t_4 *k_3*t_2^**k_1^* *E_{i11}*e^ {i\theta_1}*e^{i\theta_2}*e^{i\phi_2}\\
+t_4 *k_3*k_2^* *t_1 * E_{i11}*e^{i\phi_1}*e^{i\theta_2}*e^{i\phi_2} 
+t_4 *k_3*k_2^* *k_1*E_{i12}*e^{i\phi_1}*e^{i\theta_2}*e^{i\phi_2} \\
+k_4*k_3^* *t_2^**t_1^**E_{i12}*e^ {i\theta_1}*e^{i\theta_2}*e^{i\theta_3}
+k_4*k_3^* *t_2^**k_1^* *E_{i11}*e^ {i\theta_1}*e^{i\theta_2}*e^{i\theta_3}\\
+k_4*k_3^* *k_2^* *t_1 * E_{i11}*e^{i\phi_1}*e^{i\theta_2}*e^{i\theta_3} 
+k_4*k_3^* *k_2^* *k_1*E_{i12}*e^{i\phi_1}*e^{i\theta_2}*e^{i\theta_3} "/> (24) </center>

<center><img src="http://latex.codecogs.com/gif.latex?E_{o41} = (t_4 *k_3*t_2^**k_1^* *e^ {i\theta_1}*e^{i\theta_2}*e^{i\phi_2} 
+ t_4 *k_3*k_2^* *t_1 *e^{i\phi_1}*e^{i\theta_2}*e^{i\phi_2} \\
+ k_4*k_3^* *t_2^**k_1^* *e^ {i\theta_1}*e^{i\theta_2}*e^{i\theta_3} 
+ k_4*k_3^* *k_2^* *t_1 *e^{i\phi_1}*e^{i\theta_2}*e^{i\theta_3})*E_{i11} \\
+ (t_4 *k_3*t_2^**t_1^**e^ {i\theta_1}*e^{i\theta_2}*e^{i\phi_2}
+ t_4 *k_3*k_2^* *k_1*e^{i\phi_1}*e^{i\theta_2}*e^{i\phi_2}\\
+ k_4*k_3^* *t_2^**t_1^**e^ {i\theta_1}*e^{i\theta_2}*e^{i\theta_3}
+ k_4*k_3^* *k_2^* *k_1*e^{i\phi_1}*e^{i\theta_2}*e^{i\theta_3})*E_{i12}"/> (25) </center>

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
- t_4^**k_4^* *k_3*t_2^**k_2^* *k_1*e^{i\phi_1}*e^{i\theta_2}*e^{i\phi_2}*e^{i\theta_4}}*E_{i11}"/> (26) </center>



