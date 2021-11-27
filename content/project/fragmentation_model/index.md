---
title: Statistical properties of crumpled sheets
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
A key aspect of my research has been to better understand the statistical properties of crumpled sheets, as well as the mechanisms that can produce these statistics. As a familiar example, consider the process of crumpling a sheet of paper into a ball. Upon opening the sheet, we observe a complex network of creases where stresses sharply focused during compaction, introducing permanent, plastic deformation. We might ask how the amount of damage introduced varies with the strength of compaction, or how it is distributed spatially across the sheet.

{{< video src="unfold.mp4" autoplay="true" >}}

Crumpling is a ubiquitous phenomenon that can be observed on many different length scales, from the scale of graphene membranes up to the deformation of the earth’s crust. And while crumpling might seem an unwelcome deformation at first glance, the properties of crumpled structures can offer a number of practical advantages due to their porosity, compression-resistance, shapeability, and lightweight nature. For instance, one exciting application of crumpling is in the context of batteries and supercapacitors: Crumpled graphene electrodes are shown to have higher electrochemical surface area and resistance to aggregation owing to the high porosity and rigidity of the crumpled state[^1].

From a scientific perspective, crumpling has garnered wide interest due to surprisingly predictable behavior that can be observed amidst this very disordered process. Let's consider the simple crumpled ball experiment once again. If we crumple the same unfolded sheet a second time, new creases will develop; however, we expect the sheet to accumulate less additional damage, as it can exploit some of its existing creases during crumpling. A natural question we might ask is whether there is a rule for how such damage accumulates under repeated loading. Building on this idea, the experimental research group of Prof. Shmuel Rubinstein conducted studies of systematic crumpling by compressing a rolled sheet of Mylar with a cylindrical piston to a fixed compaction ratio, unfolding the sheet, and repeating the process. They discovered that when the total crease length accumulated is viewed as a function of crumpling iterations, the growth follows a simple logarithm[^4]:

$$\ell(n,\tilde{\Delta}) = c_1\left(1-\tilde{\Delta}\right)\log\left(1+c_2\frac{n}{\tilde{\Delta}}\right).$$

In the equation above, $\ell$ denotes total crease length, $n$ the number of crumpling iterations, and $\tilde{\Delta}$ the compaction ratio, which is the ratio of final to initial height of the piston. $c_1$ and $c_2$ are global fitting parameters. Surprisingly, this trend was robust to varying compaction ratio and initial preparations of the sheet, including pre-folding or hand-crumpling the sheet before repeated compaction.

The logarithmic scaling was a remarkable reduction of complexity in characterizing crumpling. However, a physical justification for this mathematical model was missing: Can we explain why a logarithmic relationship, in particular, arises from this process? This question motivated our follow-up work to try and explain the origin of logarithmic growth on physical grounds[^5]. We began by recognizing that as a sheet accumulates more creases over time, its surface area remains constant. Thus, rather than observing a quantity that continues to grow over time - the total crease length - we could instead look at a complementary quantity that remains invariant - the sum of individual facet areas. We found it valuable to perform the facet segmentations by hand, to ensure even the smallest facets were identified, and imaging artifacts such as faint or disconnected creases could be corrected. The facet segmentations then allowed us to observe the facet size distribution of each sheet, as well as its evolution over a series of crumples.

{{< video src="segmentation.mp4" autoplay="true" >}}

We observed that these characteristic size distributions could be accurately explained by fragmentation theory, which has a rich history in modeling natural breakup phenomena such as the crushing of rock or fragmentation of volcanic debris. Fragmentation processes can be represented by an integro-differential equation that captures the evolution of the fragment size distribution over time as follows[^6]:

$$\frac{\partial{c(x,t)}}{\partial{t}}=-r(x)c(x,t) + \int_x^{\infty}r(y)c(y,t)f(x|y)dy$$

In the equation above, $c(x,t)$ represents the number or concentration of fragments with size $x$ at time $t$, and $r(x)$ and $f(x|y)$ are the overall breakup rate and conditional breakup probability, respectively. With appropriate choices of $r(x)$ and $f(x|y)$ inferred from experimental data, the above equation can be solved exactly, with $c(x,t)$ in agreement with the observed facet size distributions. Building on the fragmentation theory framework, we likewise introduced a model for how the accumulation of damage slows down over repeated crumpling, as the average facet size becomes smaller. This allowed us to explain the logarithmic scaling seen in experiment.

The application of fragmentation theory to understand crumpling is compelling, as it offers a new perspective on a well-studied system while drawing connections to other disordered processes. Future work could explore the extent to which fragmentation theory can more broadly model damage and failure in other systems.

To learn more about this project, please see the relevant publications:
{{<cite page="/publication/comm_phys_2018" view="1" >}}
{{<cite page="/publication/nat_commun_2021" view="1" >}}

This research was also featured in:
1. [The Latest Wrinkle in Crumple Theory - _New York Times_](https://www.nytimes.com/2021/03/08/science/math-crumple-fragmentation-andrejevic.html#:~:text=From%20studies%20of%20%E2%80%9Cgeometric%20frustration,how%20paper%20folds%20under%20pressure.&text=Sign%20up%20for%20Science%20Times,cosmos%20and%20the%20human%20body.&text=can't%20sympathize%3F-,In%20a%20sense%2C%20creases%20happen%20when%20a,sheet%20of%20material%20gets%20claustrophobia.)
2. [Rock, Paper, Crumple! - _Harvard SEAS News_](https://www.seas.harvard.edu/news/2021/03/rock-paper-crumple)
3. [Crumple Theory: We Can Learn a Lot From How Paper Crumples - _HowStuffWorks_](https://science.howstuffworks.com/crumple-theory.htm#:~:text=Crumple%20Theory%3A%20We%20Can%20Learn%20a%20Lot%20From%20How%20Paper%20Crumples,-By%3A%20Patrick%20J&text=They're%20all%20undergoing%20a,fit%20into%20a%20smaller%20area.)
4. [How Paper Crumples - _Harvard Magazine_](https://www.harvardmagazine.com/2021/07/right-now-crumpled-paper)
5. [Crumple Theory: Top of Mind with Julie Rose, Episode 1576 - _BYU Radio_](https://www.byuradio.org/08a94ba5-9a5f-4010-b057-95b6fcc31a91)


[^1]: Luo, Jiayan, et al. "Compression and aggregation-resistant particles of crumpled soft sheets." _ACS Nano_ 5.11 (2011): 8943-8949.
[^2]: Amir, Ariel, Yuval Oreg, and Yoseph Imry. "On relaxations and aging of various glasses." _Proceedings of the National Academy of Sciences_ 109.6 (2012): 1850-1855.
[^3]: Lahini, Yoav, et al. "Nonmonotonic aging and memory retention in disordered mechanical systems." _Physical Review Letters_ 118.8 (2017): 085501.
[^4]: Gottesman, Omer, et al. "A state variable for crumpled thin sheets." _Communications Physics_ 1.1 (2018): 1-7.
[^5]: Andrejevic, Jovana, et al. "A model for the fragmentation kinetics of crumpled thin sheets." _Nature Communications_ 12.1 (2021): 1-10.
[^6]: Cheng, Z., and S. Redner. "Kinetics of fragmentation." _Journal of Physics A: Mathematical and General_ 23.7 (1990): 1233.






