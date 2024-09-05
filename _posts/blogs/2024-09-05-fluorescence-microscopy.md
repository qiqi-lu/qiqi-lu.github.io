---
layout: post
title: "Fluorescence Microscopy"
author: "Qiqi Lu"
category: blog
date: 2024-09-05
---

### Background Signal
When staining the objects using fluorescent dyes, some parts fo the specimen or cover glass may unwillingly be stained. This phenomenon manifests itself as barely perceptible veil covering the whole glass. 
$
I_{gt}=I_{object}+I_{background}
$

### Uneven illumination
Uneven illumination occurs when the light does not evenly illuminate your sample across the field of view. This results in darker areas and more brightly illuminated areas, most likely due to a misalighned light path in the microscope.[^1] This is usually the case if the camera or lamp is shifted relative to optical axis of the microscope.[^2]

![alt text](/assets/img/unevenillumination.png) 

### Impulse response/PSF
The impulse response of this system determining the amount and the characteristics of image blur.[^2]
- The theoretical PSF is usually based on prior knowledge of the optical system properties (confocal or wide-field microscope, objective, wavelength, etc.).
$
I_{blurred}=(I_{gt}\cdot I_{light})*PSF
$
where $I_{light}$ is the image representing the light decay effect, $\cdot$ corresponds to pixel-wise multiplication, and $*$ correspond to convolution.

### Signal detector resolution
The signal detector contributes with its pixel size, which, together with total magnification of the optical system, defines spatial sampling frequency.[^2]

### Dark current signal
There is a signal generated internally in the detector even if no photon is coming, for example, in the darkroom. 

- linearly proportional to the exposure time
- the lower the temperature, the lower the number of unwillingly generated electrons.

### Fixed pattern noise
Every CCD chip produces a small number of hot pixels, which appear as very bright pixels in the final image matrix, and dead pixels, which appear as very dark pixels.

### Quantification uncertainty
The most important noise in low-light imaging (which is typical for fluorescence microscopy) is shot noise, which is usually modeled with a Poisson distribution.

### Reference

[^1]: https://www.thermofisher.cn/cn/en/home/life-science/cell-analysis/cell-analysis-learning-center/molecular-probes-school-of-fluorescence/imaging-basics/protocols-troubleshooting/troubleshooting/uneven-illumination.html

[^2]: Svoboda, D., Kozubek, M. & Stejskal, S. Generation of digital phantoms of cell nuclei and simulation of image formation in 3D image cytometry. Cytometry Pt A 75A, 494–509 (2009).
