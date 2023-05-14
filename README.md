# KITTI Perception 

Combine object detection, instance segmentation and depth estimation. 
Play around with different methods and models and check which performs good and fast. 
In the process, learn a lot about computer vision stuff and have fun.

## Data

https://github.com/yanii/kitti-pcl/blob/master/KITTI_README.TXT

camera setup:
* camera 0 (left) is grayscale and the reference camera
* camera 2 (left) is rgb
* camera 3 (right) is rgb
* 4200 rgb imgs for each camera

calibration files:
* S_xx: 1x2 size of image xx before rectification
* K_xx: 3x3 calibration matrix of camera xx before rectification
* D_xx: 1x5 distortion vector of camera xx before rectification
* R_xx: 3x3 rotation matrix of camera xx (extrinsic)
* T_xx: 3x1 translation vector of camera xx (extrinsic)
* S_rect_xx: 1x2 size of image xx after rectification
* R_rect_xx: 3x3 rectifying rotation to make image planes co-planar
* P_rect_xx: 3x4 projection matrix after rectification

When using this dataset you will most likely need to access only P_rect_xx, as this matrix is valid for the rectified image sequences.


depth = baseline * focal / disparity
(depth = baseline * focal / (original image width * disparity))
kitti baseline = 0.54m
focal = ~721 pixels
