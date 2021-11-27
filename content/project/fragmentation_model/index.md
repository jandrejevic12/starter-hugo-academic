---
title: Fragmentation-inspired model of crumpling
#summary: An example of using the in-built project page.
tags:
- Research
date: "2021-03-05"

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
A major component of my research has been understanding the statistical properties of crumpled sheets, as well as the processes that can produce such statistics. As a familiar example, consider the process of crumpling a sheet of paper into a ball. If the crumpled sheet is opened up, we will observe a complex network of creases where stresses sharply focused during compaction, introducing permanent, plastic deformation. We might ask how the amount of damage introduced varies with the strength of compaction, or how it is distributed spatially across the sheet.

{{< video src="unfold.mp4" autoplay="true" >}}

Crumpling is a ubiquitous phenomenon that can be observed on many different length scales, from the scale of graphene membranes up to the deformation of the earth’s crust. And while crumpling might seem an unwelcome deformation at first glance, the properties of crumpled structures can offer a number of practical advantages due to their porosity, compression-resistance, shapeability, and lightweight nature. One exciting application of crumpling is in the context of batteries and supercapacitors: Crumpled graphene electrodes are shown to have higher electrochemical surface area and resistance to aggregation owing to the high porosity and rigidity of the crumpled state[^1]. From a scientific perspective, crumpling has garnered wide interest due to surprisingly predictable behavior observed amidst this very disordered process. For example, crumpled sheets exhibit slow, or logarithmic relaxation, which can be observed by tracking how the height of a crumpled ball changes after a change in the applied weight[^2]. Crumpled sheets also show predictable memory effects and aging, which is a history dependence in their relaxation[^3].

Consider the simple crumpled ball experiment once again. If we crumple the same unfolded sheet a second time, new creases will develop, but we expect the sheet to accumulate less additional damage as it can exploit some of its existing creases during crumpling. A natural question we might ask is whether there is a rule for how such damage accumulates under repeated loading. Building on this idea, the experimental research group of Prof. Shmuel Rubinstein conducted studies of systematic crumpling by compressing a rolled sheet of Mylar with a cylindrical piston to a fixed compaction ratio, unfolding the sheet, and repeating the process. They discovered that when the total crease length accumulated is viewed as a function of crumpling iterations, the growth follows a simple logarithm:

$$\ell(n,\tilde{\Delta}) = c_1\left(1-\tilde{\Delta}\right)\log\left(1+c_2\frac{n}{\tilde{\Delta}}\right).$$

In the expression above, $\ell$ denotes total crease length, $n$ the number of crumpling iterations, and $\tilde{\Delta}$ the compaction ratio, which is the ratio of final to initial height of the piston. $c_1$ and $c_2$ are global fitting parameters. Moreover, this trend was robust to varying compaction ratio and initial state of the sheet - flat, folded, or pre-crumpled.

The logarithmic scaling was a remarkable reduction of complexity in characterizing crumpling. However, a physical justification for this mathematical model was missing: Can we explain why a logarithmic relationship, in particular, arises from this process? Furthermore, why is the scaling insensitive to the spatial details of the crease network? This motivated our follow-up work to try and explain this on physical grounds. To do this, we began by recognizing that as a sheet accumulates more creases over time, its surface area remains constant - a conserved quantity. Thus, rather than observing a quantity that continues to grow over time - the total crease length - we could instead look at a complementary quantity that remains invariant - the sum of individual facet areas. While automated methods were satisfactory, we found it valuable to perform the facet segmentations by hand, to ensure even the smallest facets were identified, and imaging artifacts such as faint or disconnected creases could be corrected. The facet segmentations then allowed us to observe the facet size distribution of each sheet, as well as its evolution over a series of crumples.

{{< video src="segmentation.mp4" autoplay="true" >}}

[^1]: Luo, Jiayan, et al. "Compression and aggregation-resistant particles of crumpled soft sheets." _ACS Nano_ 5.11 (2011): 8943-8949.
[^2]: Amir, Ariel, Yuval Oreg, and Yoseph Imry. "On relaxations and aging of various glasses." _Proceedings of the National Academy of Sciences_ 109.6 (2012): 1850-1855.
[^3]: Lahini, Yoav, et al. "Nonmonotonic aging and memory retention in disordered mechanical systems." _Physical Review Letters_ 118.8 (2017): 085501.
[^4]: Gottesman, Omer, et al. "A state variable for crumpled thin sheets." _Communications Physics_ 1.1 (2018): 1-7.





