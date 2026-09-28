---
title: "MultiMaterial Pliers"
excerpt: "3D printed pliers with a flexible TPU component capable of picking up thin wires of resistors ."
header:
  image: /assets/img/pliers_main.jpeg

  teaser: /assets/img/pliers_main.jpeg
gallery:
  - image_path: /assets/img/pliers_iteration.jpeg

   
---
## Print-in-Place Designs

In many projects, it is often feasible to use a print-in-place design to 3D print parts with moving components, enabling single material extrusion without need for post-processing asesembly. Print-in-place design in used in many practical applications, such as [hinges](https://www.printables.com/model/565824-hinge-print-in-place-optimized-for-3d-printing-no-) or [bearings](https://www.printables.com/model/561588-bearings-print-in-place-with-real-rolling-elements), and some more novel objects, like [fidget toys](https://www.printables.com/model/972886-rotarings-print-in-place-rotating-fidget). This type of printing approach employs clearances around moving parts that allow for a function part immediately after removal from the print bed. However, successful execution requires careful and often complicated design and orientation of parts for proper printing, and the performance of the piece is dependent upon the accuracy of the print, which can often be affected by printing irregularities. Thus, multimaterial prints which use a combination of rigid and flexible materials, such as PLA and TPU, are often useful to circumvent this issue.

# Multimaterial Pliers
These multimaterial pliers consists of rigid PLA handles joined by a flexible 95A TPU spring. At rest, the pliers remain open, and upon compression of the handles, the jaws close together and return to their open resting postion when the compression is removed. These were designed to capably pick up resistors.

![Pliers](/assets/img/pliers_motion.gif)

# CAD Model and Design Process
Without access to multi-material printers, this design can be executed by printing the flexible and rigid pieces separately and hand pressing the parts together. These parts can be modeled together and exported separately for individual printing.

To securely connect the flexible components to the rigid, dovetails were include on the flexible component's design. Complementing holes were included on the handles and jaws to allow them to slide into place to complete the plier assembly. 

## General Size Specifications
Because of the intended purpose of these pliers, it was necessary to ensure a size that comfortably fits in the users hand while remaining functional. Further, an increased height of the pliers restricts the flexible component from moving out of plane. Thus, the following measurements were used when designing.

| Specification | Size (mm) |
| ----------- | ----------- |
| Jaw Length | 63 |
| Jaw Resting Capacity| 14.5|
| Jaw Max Capacity | 17|
| Flexible Component | 20 x 20 |
| Handle Length | 70 |
| Plier Height | 15 |


## Flexible Component
Slicer settings were leveraged to obtain the grid pattern on the flexible center component. By changing the infill density, the number of grids could be manipulated, thereby tuning the rigidity of the component and thus the capacity of the pliers. In the final model, a 20% infill density was used. At the extrusion height used, this amount allowed for easy and secure closure of the jaws while maintaining the stability of the in-plane closing motion. 

## Clearance Requirements
While a clearance around the dovetails can make the fitting of the rigid and flexible parts easier, the final assembly of the pliers used no added clearance, and the parts were hand-pressed together before being completed by hammering them in with a mallet. 

## Iterations
In general, only one iteration of printing/fitting was needed to achieve the final pliers. For efficiency, three flexible joints were printed at 20%, 25%, and 30% infill densities. The first fitting of the pliers used the 20% infill density, and the pliers were considered fully functioning with this assembly. Thus, only one set of rigid parts needed to be printed (handles, jaws). All parts were printed with a 0.6 mm nozzle. 

| | Rigid (Handles & Jaws) | Flexible (Joint) |
| ----| ----------- | ----------- |
| Material|PLA  | 95A TPU |
|Infill Pattern |  Gyroid | Grid|
| Infinill Density| 15 % | 20%|
| Perimeters| 3 | 3 |
|Top/Bottom Solid Layers | 3 | 0 |

# CAD Model

<iframe src="https://vanderbilt643.autodesk360.com/shares/public/SH90d2dQT28d5b602811173105476a813c84?mode=embed" width="640" height="480" allowfullscreen="true" webkitallowfullscreen="true" mozallowfullscreen="true"  frameborder="0"></iframe>



 




{% include gallery caption="Iterations" %}
