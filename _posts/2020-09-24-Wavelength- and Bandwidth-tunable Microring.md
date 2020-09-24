---
layout: post
title:  "Wavelength- and Bandwidth-tubable Microring"
categories: NanoPhotonic
tags: Microring
author: Zhenyu ZHAO
---

* content
{:toc}




<center> <img src = https://github.com/Hideousmon/Hideousmon.github.io/raw/master/_img/posts/Wavelength-_and_Bandwidth-_tunable_Microring.png > </center>

### Basic Equations for the coupling

$$
E_{o11} = t_1 * E_{i11} + k_1*E_{i12} \tag{1}
$$

$$
E_{o12}=t_1^**E_{i12}+k_1^* *E_{i11} \tag{2}
$$

$$
E_{o21} = t_2 * E_{i21} + k_2*E_{i22} \tag{3}
$$

$$
E_{o22}=t_2^**E_{i22}+k_2^* *E_{i21} \tag{4}
$$

$$
E_{o31} = t_3 * E_{i31} + k_3*E_{i32} \tag{5}
$$

$$
E_{o32}=t_3^**E_{i32}+k_3^* *E_{i31} \tag{6}
$$

$$
E_{o41} = t_4 * E_{i41} + k_4*E_{i42} \tag{7}
$$

$$
E_{o42}=t_4^**E_{i42}+k_4^* *E_{i41} \tag{8}
$$

### Transition Equations

$$
E_{i22} = E_{o12}*e^ {i\theta_1} \tag{9}
$$

$$
E_{i32}=E_{o22}*e^{i\theta_2} \tag{10}
$$

$$
E_{i42}=E_{o32}*e^{i\theta_3} \tag{11}
$$

$$
E_{i12} = E_{o42}*e^{i\theta_4} \tag{12}
$$

$$
E_{i21} = E_{o11}*e^{i\phi_1} \tag{13}
$$

$$
E_{i41}=E_{o31}*e^{i\phi_2} \tag{14}
$$

### Calculate Ei12

Assuming ：
$$
E_{i31} = 0
$$

#### 1. Combine (2)(4)(9)(13)

$$
\begin{align}
E_{o22} &= t_2^**(E_{o12}*e^ {i\theta_1})+k_2^* *(E_{o11}*e^{i\phi_1})\\
&= t_2^**((t_1^**E_{i12}+k_1^* *E_{i11})*e^ {i\theta_1})+k_2^* *((t_1 * E_{i11} + k_1*E_{i12})*e^{i\phi_1}) \tag{15}
\end{align}
$$

#### 2. Combine (6)(10)(15)

$$
\begin{align}
E_{o32}&=k_3^* *((t_2^**((t_1^**E_{i12}+k_1^* *E_{i11})*e^ {i\theta_1})+k_2^* *((t_1 * E_{i11} + k_1*E_{i12})*e^{i\phi_1}))*e^{i\theta_2}) \tag{16}
\end{align}
$$

#### 3. Combine (5)(10)(15)

$$
E_{o31} =  k_3*((t_2^**((t_1^**E_{i12}+k_1^* *E_{i11})*e^ {i\theta_1})+k_2^* *((t_1 * E_{i11} + k_1*E_{i12})*e^{i\phi_1}))*e^{i\theta_2}) \tag{17}
$$

#### 4. Combine (8)(11)(14)(16)(17)

$$
\begin{align}
E_{o42} = t_4^**((k_3^* *((t_2^**((t_1^**E_{i12}+k_1^* *E_{i11})*e^ {i\theta_1})+k_2^* *((t_1 * E_{i11} + k_1*E_{i12})*e^{i\phi_1}))*e^{i\theta_2}))*e^{i\theta_3})\\+k_4^* *((k_3*((t_2^**((t_1^**E_{i12}+k_1^* *E_{i11})*e^ {i\theta_1})+k_2^* *((t_1 * E_{i11} + k_1*E_{i12})*e^{i\phi_1}))*e^{i\theta_2}))*e^{i\phi_2}) \tag{18}
\end{align}
$$

#### 5. Combine (12)(18)

$$
E_{i12} = (t_4^**((k_3^* *((t_2^**((t_1^**E_{i12}+k_1^* *E_{i11})*e^ {i\theta_1})+k_2^* *((t_1 * E_{i11} + k_1*E_{i12})*e^{i\phi_1}))*e^{i\theta_2}))*e^{i\theta_3})\\+k_4^* *((k_3*((t_2^**((t_1^**E_{i12}+k_1^* *E_{i11})*e^ {i\theta_1})+k_2^* *((t_1 * E_{i11} + k_1*E_{i12})*e^{i\phi_1}))*e^{i\theta_2}))*e^{i\phi_2}))*e^{i\theta_4} \tag{19}
$$

### Calculate Eo11 with Ei11

#### 1. Solve Equation(19)

$$
E_{i12} = t_4^**k_3^* *t_2^**t_1^**E_{i12}*e^ {i\theta_1}*e^{i\theta_3}*e^{i\theta_4}
+t_4^**k_3^* *t_2^**k_1^* *E_{i11}*e^ {i\theta_1}*e^{i\theta_3}*e^{i\theta_4} \\
+t_4^**k_3^* *k_2^* *t_1 * E_{i11}*e^{i\phi_1}*e^{i\theta_2}*e^{i\theta_3}*e^{i\theta_4} 
+t_4^**k_3^* *k_2^* *k_1*E_{i12}*e^{i\phi_1}*e^{i\theta_2}*e^{i\theta_3}*e^{i\theta_4}\\
+t_4^**k_4^* *k_3*t_2^**t_1^**E_{i12}*e^ {i\theta_1}*e^{i\theta_2}*e^{i\phi_2}*e^{i\theta_4}
+t_4^**k_4^* *k_3*k_1^* *E_{i11}*e^ {i\theta_1}*e^{i\theta_2}*e^{i\phi_2}*e^{i\theta_4}\\
+t_4^**k_4^* *k_3*t_2^**k_2^* *t_1 * E_{i11}*e^{i\phi_1}*e^{i\theta_2}*e^{i\phi_2}*e^{i\theta_4} 
+t_4^**k_4^* *k_3*t_2^**k_2^* *k_1*E_{i12}*e^{i\phi_1}*e^{i\theta_2}*e^{i\phi_2}*e^{i\theta_4} \tag{20}
$$

$$
(1-t_4^**k_3^* *t_2^**t_1^**e^ {i\theta_1}*e^{i\theta_3}*e^{i\theta_4} 
- t_4^**k_3^* *k_2^* *k_1*e^{i\phi_1}*e^{i\theta_2}*e^{i\theta_3}*e^{i\theta_4} \\
- t_4^**k_4^* *k_3*t_2^**t_1^**e^ {i\theta_1}*e^{i\theta_2}*e^{i\phi_2}*e^{i\theta_4}
- t_4^**k_4^* *k_3*t_2^**k_2^* *k_1*e^{i\phi_1}*e^{i\theta_2}*e^{i\phi_2}*e^{i\theta_4})*E_{i12} \\
= (t_4^**k_3^* *t_2^**k_1^* *e^ {i\theta_1}*e^{i\theta_3}*e^{i\theta_4} 
+ t_4^**k_3^* *k_2^* *t_1 *e^{i\phi_1}*e^{i\theta_2}*e^{i\theta_3}*e^{i\theta_4} \\
+ t_4^**k_4^* *k_3*k_1^* *e^ {i\theta_1}*e^{i\theta_2}*e^{i\phi_2}*e^{i\theta_4}
+ t_4^**k_4^* *k_3*t_2^**k_2^* *t_1 *e^{i\phi_1}*e^{i\theta_2}*e^{i\phi_2}*e^{i\theta_4})*E_{i11} \tag{21}
$$

$$
\frac{E_{i12}}{E_{i11}} = \frac{t_4^**k_3^* *t_2^**k_1^* *e^ {i\theta_1}*e^{i\theta_3}*e^{i\theta_4} 
+ t_4^**k_3^* *k_2^* *t_1 *e^{i\phi_1}*e^{i\theta_2}*e^{i\theta_3}*e^{i\theta_4} \\
+ t_4^**k_4^* *k_3*k_1^* *e^ {i\theta_1}*e^{i\theta_2}*e^{i\phi_2}*e^{i\theta_4}
+ t_4^**k_4^* *k_3*t_2^**k_2^* *t_1 *e^{i\phi_1}*e^{i\theta_2}*e^{i\phi_2}*e^{i\theta_4}}{1-t_4^**k_3^* *t_2^**t_1^**e^ {i\theta_1}*e^{i\theta_3}*e^{i\theta_4} 
- t_4^**k_3^* *k_2^* *k_1*e^{i\phi_1}*e^{i\theta_2}*e^{i\theta_3}*e^{i\theta_4} \\
- t_4^**k_4^* *k_3*t_2^**t_1^**e^ {i\theta_1}*e^{i\theta_2}*e^{i\phi_2}*e^{i\theta_4}
- t_4^**k_4^* *k_3*t_2^**k_2^* *k_1*e^{i\phi_1}*e^{i\theta_2}*e^{i\phi_2}*e^{i\theta_4}} \tag{22}
$$

### Calculate Eo21 with Ei11

#### 1. Combine Equation(1)(2)(3)(9)(13)

$$
E_{o21} = (t_2 * t_1 *e^{i\phi_1}+k_2*k_1^* *e^ {i\theta_1})*E_{i11} + (t_2 * k_1*e^{i\phi_1} + k_2*t_1^**e^ {i\theta_1})*E_{i12} \tag{23}
$$

#### 2. Combine Equation(22)(23)

$$
E_{o21} = (t_2 * t_1 *e^{i\phi_1}+k_2*k_1^* *e^ {i\theta_1})*E_{i11} + (t_2 * k_1*e^{i\phi_1} + k_2*t_1^**e^ {i\theta_1})*\frac{t_4^**k_3^* *t_2^**k_1^* *e^ {i\theta_1}*e^{i\theta_3}*e^{i\theta_4} 
+ t_4^**k_3^* *k_2^* *t_1 *e^{i\phi_1}*e^{i\theta_2}*e^{i\theta_3}*e^{i\theta_4} \\
+ t_4^**k_4^* *k_3*k_1^* *e^ {i\theta_1}*e^{i\theta_2}*e^{i\phi_2}*e^{i\theta_4}
+ t_4^**k_4^* *k_3*t_2^**k_2^* *t_1 *e^{i\phi_1}*e^{i\theta_2}*e^{i\phi_2}*e^{i\theta_4}}{1-t_4^**k_3^* *t_2^**t_1^**e^ {i\theta_1}*e^{i\theta_3}*e^{i\theta_4} 
- t_4^**k_3^* *k_2^* *k_1*e^{i\phi_1}*e^{i\theta_2}*e^{i\theta_3}*e^{i\theta_4} \\
- t_4^**k_4^* *k_3*t_2^**t_1^**e^ {i\theta_1}*e^{i\theta_2}*e^{i\phi_2}*e^{i\theta_4}
- t_4^**k_4^* *k_3*t_2^**k_2^* *k_1*e^{i\phi_1}*e^{i\theta_2}*e^{i\phi_2}*e^{i\theta_4}}*E_{i11}
$$





### Calculate Eo41 with Ei11

#### 1.Combine Equation(7)(11)(14)(16)(17)(19)

$$
E_{o41} =  t_4 *k_3*t_2^**t_1^**E_{i12}*e^ {i\theta_1}*e^{i\theta_2}*e^{i\phi_2}
+t_4 *k_3*t_2^**k_1^* *E_{i11}*e^ {i\theta_1}*e^{i\theta_2}*e^{i\phi_2}\\
+t_4 *k_3*k_2^* *t_1 * E_{i11}*e^{i\phi_1}*e^{i\theta_2}*e^{i\phi_2} 
+t_4 *k_3*k_2^* *k_1*E_{i12}*e^{i\phi_1}*e^{i\theta_2}*e^{i\phi_2} \\
+k_4*k_3^* *t_2^**t_1^**E_{i12}*e^ {i\theta_1}*e^{i\theta_2}*e^{i\theta_3}
+k_4*k_3^* *t_2^**k_1^* *E_{i11}*e^ {i\theta_1}*e^{i\theta_2}*e^{i\theta_3}\\
+k_4*k_3^* *k_2^* *t_1 * E_{i11}*e^{i\phi_1}*e^{i\theta_2}*e^{i\theta_3} 
+k_4*k_3^* *k_2^* *k_1*E_{i12}*e^{i\phi_1}*e^{i\theta_2}*e^{i\theta_3} \tag{24}
$$

$$
E_{o41} = (t_4 *k_3*t_2^**k_1^* *e^ {i\theta_1}*e^{i\theta_2}*e^{i\phi_2} 
+ t_4 *k_3*k_2^* *t_1 *e^{i\phi_1}*e^{i\theta_2}*e^{i\phi_2} \\
+ k_4*k_3^* *t_2^**k_1^* *e^ {i\theta_1}*e^{i\theta_2}*e^{i\theta_3} 
+ k_4*k_3^* *k_2^* *t_1 *e^{i\phi_1}*e^{i\theta_2}*e^{i\theta_3})*E_{i11} \\
+ (t_4 *k_3*t_2^**t_1^**e^ {i\theta_1}*e^{i\theta_2}*e^{i\phi_2}
+ t_4 *k_3*k_2^* *k_1*e^{i\phi_1}*e^{i\theta_2}*e^{i\phi_2}\\
+ k_4*k_3^* *t_2^**t_1^**e^ {i\theta_1}*e^{i\theta_2}*e^{i\theta_3}
+ k_4*k_3^* *k_2^* *k_1*e^{i\phi_1}*e^{i\theta_2}*e^{i\theta_3})*E_{i12} \tag{25}
$$

#### 2. Combine Equation(22)(24)

$$
E_{o41} = (t_4 *k_3*t_2^**k_1^* *e^ {i\theta_1}*e^{i\theta_2}*e^{i\phi_2} 
+ t_4 *k_3*k_2^* *t_1 *e^{i\phi_1}*e^{i\theta_2}*e^{i\phi_2} \\
\ \\ 
+ k_4*k_3^* *t_2^**k_1^* *e^ {i\theta_1}*e^{i\theta_2}*e^{i\theta_3} 
+ k_4*k_3^* *k_2^* *t_1 *e^{i\phi_1}*e^{i\theta_2}*e^{i\theta_3})*E_{i11} \\
\ \\ 
+ (t_4 *k_3*t_2^**t_1^**e^ {i\theta_1}*e^{i\theta_2}*e^{i\phi_2}
+ t_4 *k_3*k_2^* *k_1*e^{i\phi_1}*e^{i\theta_2}*e^{i\phi_2}\\
\ \\ 
+ k_4*k_3^* *t_2^**t_1^**e^ {i\theta_1}*e^{i\theta_2}*e^{i\theta_3}
+ k_4*k_3^* *k_2^* *k_1*e^{i\phi_1}*e^{i\theta_2}*e^{i\theta_3}) \\
\ \\ 
*\frac{t_4^**k_3^* *t_2^**k_1^* *e^ {i\theta_1}*e^{i\theta_3}*e^{i\theta_4} 
+ t_4^**k_3^* *k_2^* *t_1 *e^{i\phi_1}*e^{i\theta_2}*e^{i\theta_3}*e^{i\theta_4} \\
+ t_4^**k_4^* *k_3*k_1^* *e^ {i\theta_1}*e^{i\theta_2}*e^{i\phi_2}*e^{i\theta_4}
+ t_4^**k_4^* *k_3*t_2^**k_2^* *t_1 *e^{i\phi_1}*e^{i\theta_2}*e^{i\phi_2}*e^{i\theta_4}}{1-t_4^**k_3^* *t_2^**t_1^**e^ {i\theta_1}*e^{i\theta_3}*e^{i\theta_4} 
- t_4^**k_3^* *k_2^* *k_1*e^{i\phi_1}*e^{i\theta_2}*e^{i\theta_3}*e^{i\theta_4} \\
- t_4^**k_4^* *k_3*t_2^**t_1^**e^ {i\theta_1}*e^{i\theta_2}*e^{i\phi_2}*e^{i\theta_4}
- t_4^**k_4^* *k_3*t_2^**k_2^* *k_1*e^{i\phi_1}*e^{i\theta_2}*e^{i\phi_2}*e^{i\theta_4}}*E_{i11} \tag{26}
$$

