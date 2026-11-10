---
title: "uFluidic Pinch Flow Fractionation"
excerpt: "A resin printed ufluidic mold capable of separating micro-scale particles."
header:
  image: /assets/img/ufluidic_render.PNG

  teaser: /assets/img/ufluidic_render.PNG
gallery:
  - image_path: /assets/img/ufluidic_sketch.jpeg

   
---

# Introduction

Pinch flow fractionation (PFF) is a method to size-separate nano- to micro-scale particles using channel geometries and laminar flow without outer fields (e.g., gravitational, thermal, etc.). To separate, particles are injected separately alongside a buffer medium and flowed through micro channels. These flows join at a pinched section, and particles continue their trajectory adjacent to the wall entered next to. This causes particles of any size to align against the wall. At the end of the pinch section, streamlines enter a broadened section, and the flow profile spreads. As a result, larger particles are forced closer to the center of the channel, and smaller particles follow closer to the side wall. This is caused by the center of particles following their respective streamline; naturally, larger particles have centers located farther from the channel wall, and they thus follow a trajectory closer to the middle. This process is what allows for the size-separation of particles<sup>[2](https://pubs.acs.org/ancham/article/76/18/5465/3446173/Pinched-Flow-Fractionation-Continuous-Size)</sup>.

To improve separation, enhanced PFF can be used by adding a snake-like structure in the broadened section of the device. This  snake-like structure creates a secondary pinch and broad section, replicating the effects of the initial separation. By calculating the trajectories of the particles into the first broad section, the entrance to the enhanced pinch section can be placed to collect particles, and further separate them as they enter the broad section and the distance between streamlines increases<sup>[1](https://pubs.aip.org/aip/apl/article/93/20/203507/336137/Separation-enhancement-in-pinched-flow)</sup>.

Technology such as these are useful in biomedical applications such as blood sorting. For example, it has been studied in separating cancer cells from white blood cells. Circulating tumor cells (CTCs) are desired in separations due to their importance in studying tumor characteristics in real time. However, they are in low concentration in the blood. [Podenphant et. al.](https://pubs.rsc.org/lc/article/15/24/4598/481492/Separation-of-cancer-cells-from-white-blood-cells) used an injection-molded pinch flow fractionation device to separate white blood cells from cancer cells with >90% efficiency. Other techniques, such as anti-based capture techniques, are limited as they capture only a subpopulation of CTCs and require high start-up costs and user training, which makes the process expensive and less effective. On the other hand, PFF has lower operating costs, is easy to operate, and can be single use. 

PFF devices, along with an enhanced section, can be fabricated by modeling and resin printing a mold. The section below explains the specifications I considered while designing my device.

# Designing my pinch flow fractionation device

Because it is not efficient to do multiple iterations, many parameter selections are estimations within a possible range of working values. It was necessary to pick parameters such that the separation was maximized while insuring the separator had the best probability of working.

## Widths of the first pinch and broad sections

The width of the pinch section, $w_p$, should be as small as possible. In the ideal case, it should be as large as the largest particle diameter, 150 um. Because I do not want particles to get stuck, the width of the pinch section was chosen to be 0.25 mm.

## Height of the channel
To have PFF, laminar flow is required. Thus, the width of the pinch and broad sections must be much greater than the height of that section.


For the broad section, the width to height ratio should be at least 10:1. Because the broad section width is set at 19 mm, we must ensure the height is at most 1.9 mm $(10 \times 1.9 \text{ mm} = 19 \text{ mm} = w_b)$. This should not be limiting.


For laminar flow, the ratio of width to height for the pinch section should be 2:1. Because the chosen width was 0.25 mm, the height according to that ratio should be 0.125. 

Because the height must be consistent for all channels, and the height must be great enough so that the PDMS does not bond with the glass slide, a channel height of 0.125 mm cannot be used (the largest particle diameter is 0.150 mm; this height will be too small). Thus a height of 0.5 mm will be used across the entire device.


## The lengths of the first pinch flow fractionation section

I am choosing a length of 3 mm for the pinch section.

As streamlines transition from the pinch to broadening section, the length of the broad sections should be ~ 5-10 mm. For the first broad section, I will use 10 mm.




# Enhanced pinch flow fractionation section 

To determine the final location of particles, the effects of both the first pinch flow fractionation section and the enhanced pinch flow fractionation section must be considered.



## Determining the width of the narrow enhancing segment

The enhancing section must start in a location such that it collects the particle farthest from the upper wall. Thus, we calculate particle positions from the bottom wall of the broad section using the $Y_{PFF}$ equation:

$$ Y_{PFF} = \left( w_p - \frac{D}{2} \right) \ \frac{w_b}{w_p} $$

Where $Y_{PFF}$ is the location of the radius of the particle from the lower wall. Thus, we use the 150 um particle diameter. With a $w_p = 0.25$ mm, the location of the center 150 um particle is 13.3 mm from the bottom wall. Therefore, the farthest part of the largest particle from the upper wall is:

$$13.3 \text{ mm} - 0.075 \text{ mm} = 13.225 \text{ mm}$$ 

To collect the largest diameter particle, the distance of the edge of the enhanced pinched section from the upper wall should be:

$$19 \text{ mm} - 13.225 \text{ mm} = 5.775 \text { mm} $$

To account for any irregularities in flow, an additional 0.5 mm will be added to this value (for a total of 6.275 mm from the upper wall) to ensure collection of particles. 

Thus, the narrow enhancing segment is 6.275 mm from the upper wall ($w_p = \text{6.275 mm}$).



## Determining the lengths and widths of the enhancing section

The dimensions of the enhancing section were determined by maximizing the value of $y_{EPFF}$ for the largest diameter particle, 0.150 mm, to make for the greatest separation. To do so, the hydraulic resistances of the enhancing and sink segments were calculated using the equation:

$$ R = \frac{12\eta L}{1-0.63 \left( \frac{h}{w} \right) }\times\frac{1}{h^3w} $$

Once those values are acquired, the $y_{EPFF}$ for each diameter particle can be calculated using the equation:

$$ y_{EPFF} = \left( \frac{R_E}{R_S}+1 \right) \ \frac{d_E}{w_p} \ r_p $$

Where the total resistance of the enhancing section is the sum of the hydraulic resistances of the narrow and broad enhancing sections.

Finally, to determine the dimensions, the $y_{EPFF}$ for the 0.150 mm particle was maximized by varying the width of the broad enhancing section, $d_E$ (and therefore the width of the sink section, $w_s$), and the lengths of the narrow and broad enhancing sections. 

Because a 1-3 mm space was required at the end of the enhancing section to allow the flows to reconnect before the outlets, a total of 36 mm was left for the lengths of the narrow and broad enhancing sections combined, where $L_{narrow} = 36 - 1 - L_{broad}$, and vice versa (where the -1 accounts for the width of the snake-like divider between the enhancing and sink sections).  

## Excel solver results

The following values were found using the Excel solver tool to maximize the $y_{EPFF}$ of the 0.150 mm particle.



Constant parameters (physical constants or set variables determined in previous sections):

| Parameter| Value | Units |
|--------|------|----|
| $\eta$ | 0.001 | Pa $\cdot$ s |
| channel height | 0.5 | mm |
| width of pinch section $w_p$ | 0.25 | mm |
| width of broach section $w_b$ | 19 | mm|
| width of narrow enhancing section | 6.275 | mm |
| width of snake-like structure | 1 | mm |


Variable Parameters (determined using Excel solver):

| Parameter | Value | Units |
|----|----|----|
|length of narrow enhancing section | 18 | mm |
|length of wide enhancing section | 18 | mm |
|width of wide enhancing section $d_E$ | 8.6| mm |
|width of sink section | 9.4 | mm |

$y_{EPFF}$ of each particle:

| Particle diamter (mm) | $y_{EPFF}$ (mm from upper wall)|
| ----- | ----|
|0.053| 3.30 |
|0.063 | 3.92 |
|0.125 |7.78|
|0.150 | 9.34 |


## Determining the outlet locations

The outlets must be designed so the particles of the same nominal diameter are collected into the same outlet. Thus, the boundaries must be chosen based on the $y_{EPFF}$ of the particles.


The outlet boundary between the smaller and larger particles was chosen to be 5 mm from the upper wall as the 0.063 mm and 0.125 mm diameter particles are expected to reach 3.92 mm and 7.78 mm from the upper wall, respectively. The chosen boundary is roughly in the middle of these two locations.

The outlet boundary between the larger particles and the sink need not be as precise. To ensure the middle outlet collects all of the larger diameter particles, this outlet boundary was chosen to be 10 mm away from the upper wall.

![dimensions sketch](/assets/img/ufluidic_sketch.jpeg)
# Instructions

To create a ufluidic device using resin printing, a mold of your device structure will be printed and processed, and the device will be cast with polydimethylsiloxane (PDMS) and bonded to a glass slide. 

Begin with the CAD model, which should be small enough to fit on the glass slide. In this case, the mold had a reservoir space of 25 mm wide x 75 mm long. For proper bonding, designs must start at least 3 mm in from all sides. Channels of the final device should be extruded in the CAD model, with inlets and outlets extruded beyond the top of the mold.  

<iframe src="https://vanderbilt643.autodesk360.com/shares/public/SH90d2dQT28d5b602811edbb11d43a6d3a83?mode=embed" width="640" height="480" allowfullscreen="true" webkitallowfullscreen="true" mozallowfullscreen="true"  frameborder="0"></iframe>

Once the CAD model is complete, it can be resin printed. It must be printed with the bottom face of the device parallel to the resin vat to avoid layer lines. 

Once the print is complete, care must be taken when washing. The device must be washed for ~ 10 min, but not beyond 15 min as the resin can absorb IPA. Because uncured resin will prevent the crosslinking of PDMS, turn the mold upside down at an angle to prevent IPA from pooling in the device. Once dry, inspect for any glossy areas, as this is indicative of uncured PDMS, and rewash if necessary. While cleaning, do not touch the inside of the uncured mold with your fingers or paper towel as this will increase the surface roughness and may prevent bonding.

Cure the surface of the mold for 60 seconds at room temperature with supports on. Long curing times are not necessary as they could cause warpage and mechanical strength is not required for its use.

Once cured, remove supports without touching the inside of the mold.

![ufluidic mold post-processing](https://pubs.rsc.org/lc/article/5/7/778/196447/Continuous-particle-separation-in-a-microchannel)

When the mold is complete, PDMS can be poured and cured, plasma treated, and bonded to the glass slide.

![plasma image](/assets/img/plasma_image.jpg)

# Discussion

Resin printing the mold is a significantly more cost and time efficient technique to fabricate a ufluidic device. In contrast to traditional techniques such as photolithography, resin printing requires little training and time investment, as printing time does not require the user to be present. Further, CAD designs allow for easy iteration, making resin printing fabrication of ufluidic devices accessible to anyone.
On the other hand, photolithography requires cleanroom certifications and access, making it less accessible to most users. Further, the time requirement for per device is days versus hours, and the material costs are much greater<sup>[3](https://formlabs.com/blog/microfluidics-millifluidics-lab-on-a-chip-manufacturing/)</sup>.

To handle a wider range of particle sizes, the size of the device can be increased while maintaining the width to height parameter ratios to support laminar flow (described in the section "Height of the channel"), which is required for PFF and EPFF. However, for larger particle diameters, the size of the first pinch point, $w_p$, must be greater to allow the particles to pass through, and a larger $w_p$ decreases the distance of particles relative to each other (i.e., their separation). Further, narrow pinch sections lead to more uniform spatial distribution of particles as they flow in positions closer to the wall of the pinch section, and inlet flow rates can be tailored to ensure the correct width of particle solution is maintained in the pinch section for proper wall contact<sup>[2](https://pubs.acs.org/ancham/article/76/18/5465/3446173/Pinched-Flow-Fractionation-Continuous-Size)</sup>. Thus, to achieve the desired separation, larger ufluidic devices must be used to allow space for more effective and/or additional enhanced separation sections while ensuring the necessary conditions for laminar flow are met.

The factors that limit the lower limit on particle sizes that can be separated using resin printed ufluidic devices are printing resolution and particle size relative to the pinch section<sup>[4](https://pubs.rsc.org/lc/article/5/7/778/196447/Continuous-particle-separation-in-a-microchannel)</sup>. In separating small-diameter size ranges of particles, $w_p$ must decrease. In resin printing techniques, the lower limit on this width is dependent on the resolution provided by the light source. For example, in the cases of LED arrays with a mask and lasers, the resolution is limited by the pixel size and laser spot size, respectively. In the case of our printers, the lowest theoretical $w_p$ is the pixel size, 50 um. For particle sizes $\leq$ 50 um, this limits the realizability of separation with PFF and EPFF alone. Additionally, narrow channel widths present opportunities for channel clogging. Thus, separation techniques that allow for the desired separation at larger channel widths are necessary. [Takagit et. al.](https://pubs.rsc.org/lc/article/5/7/778/196447/Continuous-particle-separation-in-a-microchannel) achieved separations of 1, 2.1, 3, and 5 um diameter particles with a pinch channel width of 20 um. Separations with particles of nominal diameter $\leq$ 10 um was accomplished using optical forces by [Heon Lee et. al](https://pubs.rsc.org/lc/article/11/2/354/336756/Enhancement-by-optical-force-of-separation-in). In this study, a pinch section width of 100 um achieved successful separation of particles due to the addition of the optical force. 


 




{% include gallery caption="Iterations" %}

