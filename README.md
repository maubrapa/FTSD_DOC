## Lightweight Traffic Sign Detection using Detachable Onboard Cameras
M. B. de Paula, A. Scapinello and C. R. Jung

A novel approach for traffic sign recognition (TSR) using off-the-shelf onboard vehicular cameras. Assuming that the camera intrinsic parameters are obtained offline, an online calibration scheme is used to estimate the extrinsic camera parameters, and Regions of Interest (ROIs) are created in the image domain based on the expected geometry and location of the traffic signs. Within these ROIs, the scale variation of the sign and background complexity are limited, allowing the development of lightweight Convolutional Neural Networks (CNNs) for TSR. Our experimental results for Brazilian traffic signs indicate that the proposed approach presents better accuracy than state-of-the-art methods at faster running times.

### Requirements
The system was implemented and tested in C++ (GCC 5.5.0 compiler), using the Open source Computer Vision library (shortly [OpenCV](https://opencv.org)) Version 3.1.0.
[Darknet YOLO v4](https://github.com/AlexeyAB/darknet) repository is also necessary. Our code uses the shared lib `darknet.so`. So dont forget to set `LIBSO=1`.

### Youtube video of results
[//]: #![snap_img_5169_1920x1080](https://user-images.githubusercontent.com/11092747/167136861-a6a4e94f-df88-4180-b009-8a137969db18.png)(https://youtu.be/Z2Htxab2mFw)

[<img src="https://user-images.githubusercontent.com/11092747/167136861-a6a4e94f-df88-4180-b009-8a137969db18.png" width="800">](https://youtu.be/Z2Htxab2mFw)

Others: https://l.ufpel.edu.br/LTSD

### Source code
`Coming soon`

### Dataset
[//]: #The dataset used in this work with the corresponding ground truth data, as well as video sequences showing the results of our method, are publicly available at...
`Coming soon`

### Pre-trained models
There are weights-file for different cfg-files (trained for our dataset):
- cropNet_1
- cropNet_3

### **mAP** (mean average precision) and processing times
[//]: #![mAP_and_processing_times](https://user-images.githubusercontent.com/11092747/167144991-46bd8e77-3915-4d02-bd89-a40e9465a1ba.png)
<img src="https://user-images.githubusercontent.com/11092747/167144991-46bd8e77-3915-4d02-bd89-a40e9465a1ba.png" width="600">
