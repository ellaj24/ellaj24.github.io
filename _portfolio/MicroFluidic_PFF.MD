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

The $w_p$ (width of the pinch section) should be as small as possible. In the ideal case, it should be as large as the largest particle diameter, 150 um. Because I do not want particles to get stuck, the width of the pinch section was chosen to be 0.25 mm.

## Height of the channel
To have PFF, laminar flow is required. Thus, the width of the pinch and broad sections must be much greater than the height of that section.


For the broad section, the width to height ratio should be at least 10:1. Because the broad section width is set at 19 mm, we must ensure the height is at most 1.9 mm $(10 \times 1.9 \text{ mm} = 19 \text{ mm} = w_b)$. This should not be limiting.


For laminar flow, the ratio of width to height for the pinch section should be 2:1. Because the chosen width was 0.25 mm, the height should be 0.125. 

Because the height must be consistent for all channels, and the height must be great enough so that the PDMS does not bond with the glass slide, it must be greater than both limitations.
Thus, a height of 0.5 will be used.


## The lengths of the first pinch flow fractionation section

I am choosing a length of 3 mm for the pinch section. I don't know why for the pinch section. 

As streamlines transition from the pinch to broadening section, the length of the broad sections should be ~ 5-10 mm. For the first broad section, I will use 10 mm.




# Enhanced Pinch Flow Fractionation Section 

To maximize separation, the $Y_{PFF}$ equation must be considered. 

Thus, we must manage the trade-off between resistance ratio and the $\frac{d_E}{w_p}$ factor.



## Determining the dimensions of the narrow enhancing segment of the enhanced pinch flow fractionation section

The enhanced section must start in a location such that it collects the particle farthest from the upper wall. Thus, we calculate particle positions from the bottom wall of the broad section using the $Y_{PFF}$ equation.

Where $Y_{PFF}$ is the location of the radius of the particle from the lower wall. Thus, we use the 150 um particle diameter. With a $w_p = 0.25$ mm, the location of the center 150 um particle is 13.3 mm from the bottom wall. Therefore, the farthest part of the 150 um from the upper wall is $13.3 \text{ mm} - 0.075 \text{ mm} = 13.225 \text{ mm}$. To collect the largest diameter particle, the distance of the edge of the enhanced pinched section from the upper wall should be $19 \text{ mm} - 13.225 \text{ mm} = 5.775 \text {mm}$. To account for any irregularities in flow, an additional 0.5 mm will be added to this value (for a total of 6.275 mm from the upper wall) to ensure collection of particles. 

Thus, the narrow enhancing segment is 6.275 mm from the upper wall.



## Determining the lengths and widths of the enhancing section

The dimensions of the enhancing section were determined by maximizing the value of $Y_{EPFF}$ for the largest diameter particle, 0.150 mm, to make for the greatest separation. To do so, the hydraulic resistances of the enhancing and sink segments were calculated using the formulas:

$$ R = \frac{12\eta L}{1-0.63(\frac{h}{w})}\times\frac{1}{h^3w} $$

The length of the enhanced pinching section will be 3 mm, and the broad section will be 33 mm. An additional gap of length 3 mm will be added at the end of this section so the sink and enhancing streams can reconnect before reaching the collection outlets.


# Determining the location of outlet sections based on the $Y_{EPFF}$ of the largest diameter particle

To do so, we must use *eq for $Y_{EPFF}$ with resistances plugged in* to maximize $Y_{EPFF}$. We will need to determine the largest wide enhancing segment, $d_E$, that maximizes this value.

After some calculations, it was determined that $d_E = 12$ mm was the best choice for this.

Based on this, the locations of the small and large particles from the upper wall, $Y_{EPFF}$, can be calculated to determine the outlet locations.

## Calculating $Y_{EPFF}$ of particles

For the upper outlet location, consider the $Y_{\text{EPFF}}$ of the larger small particle of diameter $0.063\text{ mm}$, which will be the farthest from the upper wall. Its bottom edge will be located $2.42\text{ mm}$ from the upper wall.

To determine the location of the middle outlet section, consider locations of the large-diameter particles. The $Y_{\text{EPFF}}$ of the $0.125\text{ mm}$ particle is $4.74\text{ mm}$ from the upper edge. Thus, its top edge will be located $4.68\text{ mm}$ from the upper wall. The largest diameter particle center from the upper wall is $Y_{\text{EPFF}} = 5.69\text{ mm}$. To account for the radius, the bottom edge of the particle will be $5.76\text{ mm}$ from the upper wall.

## Determining best outlet locations

Therefore, we predict that the farthest edge of the smaller particle outlet should be at $2.42\text{ mm}$ from the upper wall. The middle section to collect the larger particles should begin at the top edge of the smaller large particle, $4.68\text{ mm}$ from the upper wall, and end at the bottom edge of the largest particle, $5.76\text{ mm}$ from the upper wall.

Therefore, the divide between the top and middle outlets should be between the lowest smallest particle and the highest larger particle, between 2.42 and 4.68 mm. Thus, the divide will be at 3.5 mm.

The divide between the middle and bottom outlet sections will be ~ $d_E$ to keep flows consistent.

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

