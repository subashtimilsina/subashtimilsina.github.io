---
layout: page
title: Quantized Spectrum Cartography via Tensor Decomposition and GANs.
description: Mutli-dimensional data arrays (Tensors) completion from incomplete and quantized measuremnts using machine learning and deep learning.
img: assets/img/New_sc_illustration.jpg
importance: 3
category: After 2020
related_publications: false
---

## **Introduction**

Spectrum Cartography, or Radio Map Estimation, is like making a map that shows how strong or weak radio signals (like Wi-Fi or cellular signals) are in different places and different frequency bands. Imagine you're walking around with your phone, and at each spot, you check how good the signal is—maybe it's strong near a tower but weak far away. The goal is to create a full map that shows the signal strength everywhere and different frequency bands, even in places where you didn’t actually measure it.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/figure4_quantsc.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/figure2_quantsc.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>


## **Applications:**
  - **Better Coverage:** Helps phone companies figure out where signals are good and where they need to improve, like finding "dead zones."
  - **Less Interference:** Shows where signals from different sources overlap and might cause problems.
  - **Network Planning:** Helps decide where to put things like cell towers to give better service.

---

## **Reproducibility:**
- [Source Code](https://github.com/subashtimilsina/Quantized-Radio-Map-Estimation-BTD-and-DGM)
- [Paper 1 IEEE ICASSP 2023 (Introduced deep model)](https://ieeexplore.ieee.org/abstract/document/10096058?casa_token=osyD2IS_sfcAAAAA:S7q96S-NCOpvEeK0IAgohCb3lWN3nF8dmAbQualWEQRZGazeubOWpowCeNMI_E29Hnn18ZmtlQ)
- [Paper 2 IEEE TSP 2023 (Theoretical guarantees and BTD model)](https://ieeexplore.ieee.org/abstract/document/10335642?casa_token=OZLP8v8gUOMAAAAA:xx7jQ-t08FFovgmy0T7SPsOSW4Gpc8q0mfskZWalcycr38ihtmBgwk2A_-wroz5J_V_CcPKr6g)
- <a href="/assets/pdf/quant_sc.pdf" target="_blank">Download slides</a>

---
# **Overview:**
Mathematically, the problem is to **recover the high-dimensional tensor from few measurements.**
<div class="col-sm mt-3 mt-md-0">
    {% include figure.liquid loading="eager" path="assets/img/figure3_quantsc.png" title="example image" class="img-fluid rounded z-depth-1" %}
</div>

<div class="caption">
    Spectrum cartography illustration.
</div>

# **Challenges:**
- Indoor environment has interference so the power propagation in the space is not smooth i.e. this is called heavy shadowing scenarios. 
- Handcrafted priors such as low-rank and sparsity prior fails to capture such complex scenarios. This requires complex function, and the obvious choice is to learn the deep neural network.
- Sending real-valued measurements is not feasible due to communication overhead, limited bandwidth, latency. So, the measurements are quantized
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/figure1_quantsc.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/figure5_quantsc.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

<div class="caption">
    Shadowing (left), 3-bit quantized measurement (right).
</div>

# **Methodology**

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/figure6_quantsc.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

## Maximum Likelihood Formulation with deep generative network

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/figure7_quantsc.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

## Deep Generative model to model complex data distribution

<div class="row justify-content-sm-center">
    <div class="col-sm-6 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/figure8_quantsc.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-6 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/figure9_quantsc.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Training GAN to generate <b>spatial loss field</b> (SLF), Decomposition model.
</div>

