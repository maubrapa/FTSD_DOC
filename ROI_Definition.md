### Definition of the ROIs
The proposed system is also aimed at low-cost solutions, in which a detachable camera (e.g., a smartphone) is placed at 
the top-central portion of the windshield, monitoring the road ahead, as illustrated bellow.

![worldAndCameraCoordinates](https://github.com/maubrapa/FTSD_DOC/assets/11092747/b3a8951f-1c66-42c3-aff6-f05deeb1a1e6)

Fig. 1.: 3D world and camera coordinate

Hence, the extrinsic camera parameters are characterized by the camera height $h$ and the pitch ($\alpha$), yaw ($\beta$) and roll
($\gamma$) angles. In this work, we consider that there is no roll (since such movement is usually prevented by the windshield), 
and estimate the remaining parameters using the online self-calibration scheme presented [1]. This method assumes that
the camera intrinsic parameters are known (they can be easily obtained using publicly available toolboxes such 
as [2], and are always fixed if the focal length of the camera does not change), 
and explore the expected geometry of a flat planar road with dashed lane markings. Hence, it allows a very flexible
setup, in which the user may attach the camera differently every time they enter the vehicle, and detach
it when leaving.

With the fully calibrated camera, the next step is to identify the region in the WCS where traffic signs are expected to lie on, and then project it to the ICS using the known camera parameters. 

Given a 3D point $\Large x_w=(x_w,y_w,z_w)^T$ in the WCS, the corresponding point $\Large x_c=(x_c,y_c,z_c)^T$ in the 3D camera coordinate system is given by a rigid transformation:

```math
\Large
{x}_c = R\left({x}_w-{x}_0\right), 
```

where $\Large {x}_0=(h,0,0)^T$ is the center and $\Large R$ is the rotation matrix of the camera. The corresponding projection of $\Large {x}_c$ into an image pixel $\Large {u}=(u,v)^T$ is given by

```math
\Large
u= \frac{f_ux_c}{z_c}, \text{~~} v =
\frac{f_vy_c}{z_c},
```

where $\Large f_u$ and $\Large f_v$ are the pixel focal lengths of the camera, and $\Large (u,v)^T$ are image coordinates relative to the optical axis $\Large (u_o,v_o)^T$ of the camera. 

In the WCS, the ROIs are rectangles orthogonal to both the ground plane and the central axis of the road. We define a rectangular region $r$, at a distance $\Large \delta_z$ meters along the vertical axis in a birds-eye view, as shown in \figref{fig:definicaoROI} (left). The region is defined by its width $\Large \delta_w$ (in meters) and height $\Large \delta_h$ (in meters), as well as its central position $\Large {w}_z$ given by

```math
\Large
{w}_z = \left(
p_h + \frac{p_d}{2}, 
\delta_y, 
\delta_z
\right)^T, 
```

where $\Large \delta_y$ is the approximate lateral distance from the vehicle location to the center of the sign, $\Large p_d$ and $\Large p_h$ are the expected diameter and height (computed from the ground to the bottom of the sign) of the vertical sign, respectively, and $\delta_z$ is the distance from the ROI to the camera. Figure 2 illustrates geometrically the parameters involved in equation above, as well as the rectangular ROI reprojected to the ICS (in the right).

![definicaoROI_new4](https://github.com/maubrapa/FTSD_DOC/assets/11092747/6bff3523-2074-4cf0-89ab-7980e0a65cfe)

Fig. 2.: Region of interest in world coordinate system (left). Reprojection of the image regions (right)

> **Note**<br>
More details in paper

<hr style="border:1 px solid gray">

### References

[1] 
M. B. De Paula, C. R. Jung, and
L. G. Da Silveira, Jr., “Automatic on-
the-fly extrinsic camera calibration of
onboard vehicular cameras,” Expert Syst.
Appl., vol. 41, no. 4, pp. 1997–2007,
Mar. 2014. [Online]. Available: http:
//dx.doi.org/10.1016/j.eswa.2013.08.096

[2]
J. Y. Bouguet, “Camera calibration toolbox for Matlab,” 2008. [Online].
Available: http://www.vision.caltech.edu/ bouguetj/calib doc/
