---
title: Computational modeling of crumpling dynamics
#summary: An example of using the in-built project page.
tags:
- Research
date: "2021-11-01"

# Optional external URL for project (replaces project detail page).
#external_link: ""

image:
  #caption: Photo by rawpixel on Unsplash
  focal_point: Smart

links:
#- icon: twitter
#  icon_pack: fab
#  name: Follow
#  url: https://twitter.com/georgecushen
url_code: ""
url_pdf: ""
url_slides: ""
url_video: ""

# Slides (optional).
#   Associate this project with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides = "example-slides"` references `content/slides/example-slides.md`.
#   Otherwise, set `slides = ""`.
#slides: example
---
As part of my current research, I have been developing a large-scale simulation of thin, elastoplastic sheets to aid our study and analysis of crumpling dynamics.  

A popular model for elastic materials is a mass-spring system: a collection of discrete nodes that interact with their neighbors via linear springs. This simple framework can accurately reproduce continuum elastic properties of the material.

{{< figure src="mass_spring_model.png">}}

In our work, we build on the widely-used elastic membrane model of Seung and Nelson[^1] and extend it to simulate self-avoiding, elastoplastic sheets. A key consideration in our implementation is the numerical procedure used to integrate the equations of motion for the sheet. We recognize that a sheet undergoing crumpling exhibits deformations on two different timescales: a slower timescale for wide-range smooth deformation, and a faster timescale for rapid buckling and local changes in velocity. This motivates two different formulations of the equations of motion: a quasistatic formulation in which acceleration is approximated as zero, and a dynamic formulation that retains acceleration as non-negligible. The quasistatic formulation may be efficiently integrated using an implicit scheme, while the dynamic formulation is handled explicitly. The complete model is implemented in C++ and multithreaded using OpenMP, and a paper for this work is currently in preparation.

{{< video src="radial_crumple.mp4" controls="yes" >}}

The video above demonstrates one example simulation of a thin sheet radially confined into a ball. The sheet is modeled by 46767 nodes and 92716 triangles distributed randomly in a square domain. The sheet is compressed by a radial potential that mimics a spherical shell with decreasing radius. Short-range repulsive forces enforce the sheet’s self-avoidance, and plastic damage accumulates as regions of the sheet develop a large enough local curvature. Particularly interesting is the observation of individual snap-throughs of flat surfaces as the sheet locks in creases. The cross-sectional view midway through the video also reveals a high degree of layering of the sheet. After compressing for a time, the radius of the enclosing shell begins to increase, allowing the crumpled sheet to relax. At the end, the relaxed state of the sheet displays permanent plastic damage.

[^1]: Seung, Hyunjune Sebastian, and David R. Nelson. "Defects in flexible membranes with crystalline order." _Physical Review A_ 38.2 (1988): 1005.

