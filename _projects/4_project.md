---
layout: page
title: Sound Source Localization With Noise Filtration Using Deep Networks.
description: Undergraduate Thesis.
img: assets/img/SSL_Robot.jpg
importance: 3
category: Before 2020
---

## **Objective:**
To develop a sound localization system that can locate the human voices in disaster zones using an omni-directional vehicle equipped with a cubical microphone array. The system aims to aid in search-and-rescue operations where visibility is limited.

---

## **Demo:**

<iframe width="560" height="315" src="https://www.youtube.com/embed/Y1u37uJwSeI" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>

## **Overview:**
This project focuses on developing a **real-time 3D sound source localization system** that uses a cubical microphone array, intelligently designed to be mounted on a mobile robot for autonomous navigation towards sound sources. The system incorporates **voice activity detection** and **deep learning-based denoising** techniques to filter the background noise and improve the accuracy of detecting the direction of arrival of sound sources. By calculating the time difference of arrival (TDOA) between microphones, the system determines the delay in sound reaching each one. It then applies the GCC-PHAT algorithm to perform cross-correlation between signals. A 3D grid is constructed around the microphone array, and the peaks in cross-correlation on the grid are used to precisely estimate the azimuth and elevation of the sound sources.

---

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/cube array.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/SSL_Robot.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Left : (Cubical microphone array), Right : (Whole system)
</div>

## **Technologies:**
- **Hardware:**
  - Cubical microphone array with eight microphones arrangement
  - Three-wheel omni-directional drive system
  - Raspberry Pi 3
  - Atmega2560 micro-controller for vehicle control

- **Software:**
  - Python, C++, Keras

---

## **Reproducibility:**
- [Source Code](https://github.com/subashtimilsina/Sound-Source-Localization/)
- [Hardware Details](https://github.com/subashtimilsina/Sound-Source-Localization-Hardware)
- [Please check paper for more detail](http://idl.iscram.org/files/abhishkhanal/2020/2293_AbhishKhanal_etal2020.pdf)

---

## **Methodology:**

1. **Microphone Array Configuration:**
   - A cube-shaped microphone array, fabricated from aluminum for lightweight, contains eight microphones mounted on four vertical faces. The microphones capture sound data to estimate the position of a stationary sound source in 3D space.

2. **Voice Activity Detection and Noise Filtration:**
   - Deep Learning-based Convolutional Encoder-Decoder (CED) is used on Fourier transformed sound signals to first remove environmental noise from the sound signal also the signal typically consists of environmental noise, the desired sound source, and silent frames, Voice Activity Detection (VAD) is employed to trigger the localization process only when a voice is detected.
   
3. **Sound Source Localization:**
   - The system uses Time Difference of Arrival (TDOA) to calculate the delay between sound reaching different microphones. Using the GCC-PHAT algorithm, cross-correlation is performed between signals to accurately estimate azimuth and elevation angles.
   
4. **Grid Search Algorithm:**
   - A 3D grid is constructed around the microphone array, and the sound localization is performed by summing the results of GCC-PHAT over multiple microphone pairs. The highest peaks on the grid correspond to the direction of the sound source.

5. **Vehicle Navigation:**
   - Once the sound source's azimuth and elevation angles are computed, the system autonomously drives the omni-directional vehicle towards the detected sound. The vehicle uses these angles to adjust its movement in real-time.

<div class="col-sm mt-3 mt-md-0">
    {% include figure.liquid loading="eager" path="assets/img/flow chart.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
</div>

---

## **Key Features:**
- **3D Sound Localization:** Detects and locates sound sources in 3D space within standard deviation of 1 degree error using a grid search method.
- **Autonomous Navigation:** The system is integrated with a three-wheeled omni-directional vehicle, allowing it to autonomously navigate towards the sound source.
- **Robust to Noises:** The use of auto-encoder architecture for filtering echoes and noises.
- **Human Voice Detection:** Specifically designed to localize stationary human voices in disaster scenarios where visibility is limited.

---

## **Conclusion:**
This project demonstrates a practical approach to sound source localization for disaster victim search-and-rescue operations. With further enhancements, it has the potential to become an invaluable tool in emergency response scenarios.

