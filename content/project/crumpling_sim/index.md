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
As part of my current research with Prof. Chris Rycroft, I have been developing a large-scale simulation of thin, elastoplastic sheets to aid our study and analysis of crumpling dynamics. The simulation is implemented in C++ and multithreaded using OpenMP. Specific components of the numerical implementation will be discussed separately; the video below demonstrates one example simulation of a thin sheet radially confined into a ball.

{{< video src="radial_crumple.mp4" controls="yes" >}}

The sheet is modeled as a triangulated lattice of discrete nodes which interact with their neighbors via stretching, bending, and damping forces. The example shown consists of 46767 nodes and 92716 triangles distributed randomly in a square domain. The sheet is compressed by a radial potential that mimics a spherical shell with decreasing radius. Short-range repulsive forces enforce the sheet’s self-avoidance, and plastic damage accumulates as regions of the sheet develop a large enough local curvature. Particularly interesting is the observation of individual snap-throughs of flat surfaces as the sheet locks in creases. The cross-sectional view midway through the video also reveals a high degree of layering of the sheet. After compressing for a time, the radius of the enclosing shell begins to increase, allowing the crumpled sheet to relax. The relaxed state of the sheet displays permanent plastic damage.
