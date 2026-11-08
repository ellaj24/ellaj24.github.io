---
title: "uFluidic Pinch Flow Fractionation"
excerpt: "A resin printed ."
header:
  image: /assets/img/pliers_main.jpeg

  teaser: /assets/img/pliers_main.jpeg
gallery:
  - image_path: /assets/img/pliers_iteration.jpeg

   
---
Because it is not efficient to do multiple iterations, many parameter selections are estimations within a possible range of working values. It was necessary to pick parameters such that the separation was maximized while insuring the separator had the best probability of working.

## Widths of the first pinch and broad sections

The width of the pinch section, $w_p$, should be as small as possible. In the ideal case, it should be as large as the largest particle diameter, 150 um. Because I do not want particles to get stuck, the width of the pinch section was chosen to be 0.25 mm.

## Height of the channel
To have PFF, laminar flow is required. Thus, the width of the pinch and broad sections must be much greater than the height of that section.


For the broad section, the width to height ratio should be at least 10:1. Because the broad section width is set at 19 mm, we must ensure the height is at most 1.9 mm $(10 \times 1.9 \text{ mm} = 19 \text{ mm} = w_b)$. This should not be limiting.


For laminar flow, the ratio of width to height for the pinch section should be 2:1. Because the chosen width was 0.25 mm, the height according to that ratio should be 0.125. 

Because the height must be consistent for all channels, and the height must be great enough so that the PDMS does not bond with the glass slide, a channel height of 0.125 mm cannot be used (the largest particle diameter is 0.150 mm; this height will be too small). Thus a height of 0.5 mm will be used across the entire device.


## The lengths of the first pinch flow fractionation section

I am choosing a length of 3 mm for the pinch section. I don't know why for the pinch section. 

As streamlines transition from the pinch to broadening section, the length of the broad sections should be ~ 5-10 mm. For the first broad section, I will use 10 mm.




# Enhanced Pinch Flow Fractionation Section 

To maximize separation, the $Y_{PFF}$ equation must be considered. 

Thus, we must manage the trade-off between resistance ratio and the $\frac{d_E}{w_p}$ factor.



## Determining the dimensions of the narrow enhancing segment of the enhanced pinch flow fractionation section

The enhanced section must start in a location such that it collects the particle farthest from the upper wall. Thus, we calculate particle positions from the bottom wall of the broad section using the $Y_{PFF}$ equation:

$$ Y_{PFF} = \left( w_p - \frac{D}{2} \right) \ \frac{w_b}{w_p} $$

Where $Y_{PFF}$ is the location of the radius of the particle from the lower wall. Thus, we use the 150 um particle diameter. With a $w_p = 0.25$ mm, the location of the center 150 um particle is 13.3 mm from the bottom wall. Therefore, the farthest part of the 150 um from the upper wall is $13.3 \text{ mm} - 0.075 \text{ mm} = 13.225 \text{ mm}$. To collect the largest diameter particle, the distance of the edge of the enhanced pinched section from the upper wall should be $19 \text{ mm} - 13.225 \text{ mm} = 5.775 \text {mm}$. To account for any irregularities in flow, an additional 0.5 mm will be added to this value (for a total of 6.275 mm from the upper wall) to ensure collection of particles. 

Thus, the narrow enhancing segment is 6.275 mm from the upper wall.



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


Variable Parameters (determined 

| Parameter | Value | Units |
|----|----|----|
|length of narrow enhancing section | 18 | mm |
|length of wide enhancing section $d_E$ | 18 | mm |
|width of wide enhancing section | 8.6| mm |
|width of sink section | 9.4 | mm |

$y_{EPFF}$ of each particle

| Particle diamter (mm) | $y_{EPFF}$ (mm from upper wall)|
| ----- | ----|
|0.053| 3.30 |
|0.063 | 3.92 |
|0.125 |7.78|
|0.150 | 9.34 |


## Determining the outlet locations

The outlets must be designed so the particles of the same nominal diameter are collected into the same outlet. Thus, the boundaries must be chosen based on the $y_{EPFF}$ of the particles.


The outlet boundary between the smaller and larger particles was chosen to be 5 mm from the upper wall as the 0.063 mm and 0.125 diameter particles are expected to reach 3.92 mm and 7.78 mm from the upper wall, respectively. The chosen boundary is roughly in the middle of these two locations.

The outlet boundary between the larger particles and the sink need not be as precise. To ensure the middle outlet collects all of the larger diameter particles, this outlet boundary was chosen to be 10 mm away from the upper wall.




![Pliers](/assets/img/pliers_motion.gif)



| Specification | Size (mm) |
| ----------- | ----------- |
| Jaw Length | 63 |
| Jaw Resting Capacity| 14.5|
| Jaw Max Capacity | 17|
| Flexible Component | 20 x 20 |
| Handle Length | 70 |
| Plier Height | 15 |



# CAD Model

<iframe src="https://vanderbilt643.autodesk360.com/shares/public/SH90d2dQT28d5b602811173105476a813c84?mode=embed" width="640" height="480" allowfullscreen="true" webkitallowfullscreen="true" mozallowfullscreen="true"  frameborder="0"></iframe>



 




{% include gallery caption="Iterations" %}

