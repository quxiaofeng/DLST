## Deep Specific-Location Tracking

Created by Lingxiao Yang at PolyU at HongKong.


#### Introduction

Deep Specific-Location Tracking (DLST) is an tracking framework based on deep convolutional networks, which decouples the tracking problem into two sub-tasks: localization and classification. The localization is a preprocess step to estimate the target location in the current frame. The output of localization with target position in the previous frames are both utilized to generate samples for further classification.

This code has been tested on Windows 10 64-bit and Ubuntu on MATLAB 2015a/2016b.


#### Installation

**Prerequisites**
	
1. MATLAB (2015a/2016b).

2. MatConvNet (with version 1.0-beta23 or above).
	
3. For GPU support, a GPU at least 2GB memory is needed. 
	
4. Cuda toolkit 7.5 or above (8.0) is required. Cudnn is optional. 

5. OpenCV 3.0 (3.1) and MexOpencv are needed if you want faster speed.

**How to run the Code**

1. Compile the MatConvNet according to the [website](http://www.vlfeat.org/matconvnet/)

2. Compile the OpenCV and MexOpenCV if you need faster speed. Otherwise, please comment the line 98
in ``utils/im_crop.m``, and uncomment the line 93-94 to use the matlab ``imresize`` function (around 2x slower).

3. Change the path to your local path in ``setupDLST.m`` and the local tracker model path in ``utils/getDefaultOpts.m (opts.model)``.

4. If you want create your own tracker model, please see the details in ``createDLST.m``. Currently, we only adopt VGG-M model
for our paper.

5. For VOT2016 testing, please install the [VOT official toolkit](https://github.com/votchallenge/vot-toolkit), and simply 
copy the ``DLST\VOT2016\wrapper\tracker_DLST.m`` to your VOT workspace. 


#### Packed Results for OTB and VOT2016

It is very time consuming for running this code on entire OTB and VOT2016 datasets. Ususally it will take around 1 day for OTB 
testing (One-Pass), and 3 ~ 4 days for VOT2016 evaluation. You can simply download the results from following link.

[BaiduYun](https://pan.baidu.com/s/1gfvfyjL) [OneDrive](https://1drv.ms/f/s!AjoDviVXbtjXgyzr_Nnc16AUS_yO)


#### Citation

	accepted by ACM MM 2017, bib will be coming soon

#### License

This software is being made available for research purpose only. 

As we utilize or re-implement many function from project [MDNet](https://github.com/HyeonseobNam/MDNet) and 
[RCNN](https://github.com/rbgirshick/rcnn). please check their licence files for details.