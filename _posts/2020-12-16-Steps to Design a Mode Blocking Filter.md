---
layout: post
title:  "Steps to Design a Mode Blocking Filter"
categories: NanoPhotonic
tags: mode blocking filter
author: Zhenyu ZHAO
---

* content
{:toc}


## Theory
<center> <img src="http://latex.codecogs.com/gif.latex? n_{SWG}^2 = \delta*n_{Si}^2 + (1-\delta)*n_{Clad}^2"/>  <div align="right"> (1) </div>  </center>

where:

<div> <img src="http://latex.codecogs.com/gif.latex? \delta"/> is the duty cycle (Si Part). </div>

<div> <img src="http://latex.codecogs.com/gif.latex? n_{Si} "/>   and  <img src="http://latex.codecogs.com/gif.latex? n_{Clad} "/>   can be derived from Lumerical Mode Simulation. </div>

Then, the phase matching condition:
<center> <img src="http://latex.codecogs.com/gif.latex? n_{bus} + n_{SWG} = \frac{\lambda}{\Lambda}"/>  <div align="right"> (2) </div>  </center>

where:
<div> <img src="http://latex.codecogs.com/gif.latex? \lambda"/> is the operation wavelength. </div>

<div> <img src="http://latex.codecogs.com/gif.latex? \Lambda"/> is the grating period. </div>

<div> <img src="http://latex.codecogs.com/gif.latex? n_{bus}"/>  is the effective indices of the target mode in bus waveguide. </div>




## Design Steps

1. <div> <img src="http://latex.codecogs.com/gif.latex? n_{bus} "/> is known and can be derived from MODEsimulation. </div>
2. <div> decide  <img src="http://latex.codecogs.com/gif.latex?  \lambda "/> .</div>
3. <div>decide side waveguide width, then <img src="http://latex.codecogs.com/gif.latex? n_{Si} "/>   and  <img src="http://latex.codecogs.com/gif.latex? n_{Clad} "/>   is decided, and can be derive from MODE. </div>  
4. <div>select a <img src="http://latex.codecogs.com/gif.latex? \delta "/>   , then calculate  <img src="http://latex.codecogs.com/gif.latex? \Lambda "/>.  </div> 



## Reference

[1] Yu He, Yong Zhang, Hongwei Wang, and Yikai Su, "On-chip silicon mode blocking filter employing subwavelength-grating based contra-directional coupler," Opt. Express **26**, 33005-33012 (2018)