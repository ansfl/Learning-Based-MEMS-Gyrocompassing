&nbsp; &nbsp;  &nbsp;  &nbsp; &nbsp;  &nbsp;  &nbsp; &nbsp;  &nbsp;  &nbsp; &nbsp;  &nbsp;  &nbsp; &nbsp;  &nbsp;  &nbsp;  <img src="https://github.com/ansfl/MEMS-IMU-Denoising/blob/main/figrues/Logo.png?raw=true" width="500" />

<!-- # MEMS-IMU-Denoising
This repository contains both code and experimental data associated with our paper "Parametric and State Estimation of Stationary MEMS-IMUs: A Tutorial". -->

### Introduction
Inertial navigation systems (INS) are widely used in both manned and autonomous platforms. One of the most critical tasks prior to their operation is to accurately determine their initial alignment while stationary, as it forms the cornerstone for the entire INS operational trajectory. While low-performance accelerometers can easily determine roll and pitch angles (leveling), establishing the heading angle (gyrocompassing) with low-performance gyros proves to be a challenging task without additional sensors. While in stationary conditions, each measurement was recorded at a sampling rate of 600 Hz for 4 minutes, maintaining an average interval of 5$^\circ$ across the entire 360$^\circ$ azimuth plane. The overall dataset comprises 80 samples, randomly split into training, validation, and test sets with a ratio of 70:10:20, where training was conducted using a single Nvidia T4 GPU. 

&nbsp;  &nbsp;  &nbsp; &nbsp;  &nbsp; &nbsp; &nbsp; &nbsp;  &nbsp; &nbsp; &nbsp;  &nbsp;  &nbsp; &nbsp;  &nbsp; &nbsp; 
 <img src="https://github.com/ansfl/Learning-Based-MEMS-Gyrocompassing/blob/main/figures/Fig_measurement.png?raw=true" width="600" class='center'/>

The figure above provides a representative visualization of a random gyroscope sample lasting 4-minute across all three 3 channels, resulting in a dimensionality of 144,000$\times$3. While the dense measurements form the colored background for each axis, their corresponding sample means are marked with dashed lines to emphasize the specific axial projection of $\omega_{ie}$. Next, to examine the instrumental noise under steady-state conditions, a 1-hour static measurement is recorded, and the well-known Allan Variance (AV) analysis is then performed to quantify error dynamics through extensive time averaging:

&nbsp;  &nbsp;  &nbsp; &nbsp;  &nbsp; &nbsp; &nbsp; &nbsp;  &nbsp; &nbsp; &nbsp;  &nbsp;  &nbsp; &nbsp;  &nbsp; &nbsp; 
 <img src="https://github.com/ansfl/Learning-Based-MEMS-Gyrocompassing/blob/main/figures/Fig_AV.png?raw=true" width="600" class='center'/>

 &nbsp;  &nbsp;  &nbsp; &nbsp;  &nbsp; &nbsp; &nbsp; &nbsp;  &nbsp; &nbsp; &nbsp;  &nbsp;  &nbsp; &nbsp;  &nbsp; &nbsp; 
 <img src="https://github.com/ansfl/Learning-Based-MEMS-Gyrocompassing/blob/main/figures/fig_w_ie.png?raw=true" width="600" class='center'/>

 &nbsp;  &nbsp;  &nbsp; &nbsp;  &nbsp; &nbsp; &nbsp; &nbsp;  &nbsp; &nbsp; &nbsp;  &nbsp;  &nbsp; &nbsp;  &nbsp; &nbsp; 
 <img src="https://github.com/ansfl/Learning-Based-MEMS-Gyrocompassing/blob/main/figures/Fig_GC_ML.png?raw=true" width="600" class='center'/>


To circumvent this deficiency, in this study we present a practical deep learning framework to effectively compensate for the inherent errors in low-performance gyroscopes. By learning its temporal and spatial error patterns, our model demonstrates robustness to internal and environmental disturbances, allowing for accurate gyrocompassing within shorter time intervals. Our main contribution lies in three key aspects: 

* Our learning framework is tailor-made for MEMS-based sensors, reducing waiting times by a factor of ten or, alternatively, cutting alignment error by over 50\%.

* Thorough evaluation: Errors undergo initial theoretical analysis before being experimentally validated across a diverse range of orientations.

* Open-source accessibility: To allow a first-person impression, both code and data are openly shared in this repository, enabling transparent reproduction of our results.


### Dataset

The data in this work was obtained from a dedicated apparatus for alignment and synchronization of two arrays of five inertial MEMS-IMUs. 

*"Xsens DOT sensor provides 3D angular velocity using a gyroscope, 3D acceleration using accelerometer and 3D earth magnetic field using a magnetometer. Combined with Xsens sensor fusion algorithms, 3D orientation and free acceleration are provided. With the wireless nature of Bluetooth 5.0, Xsens DOT sensor is an excellent measurement unit for tracking human body motions"* ([Xsense-DOT](https://www.xsens.com/hubfs/Downloads/Manuals/Xsens%20DOT%20User%20Manual.pdf))

&nbsp; &nbsp; &nbsp;  &nbsp;  &nbsp; &nbsp;  &nbsp;  &nbsp; &nbsp;  &nbsp; &nbsp;  &nbsp;  &nbsp; &nbsp;  &nbsp;  &nbsp; &nbsp;  &nbsp;  &nbsp; &nbsp;  &nbsp;  &nbsp; <img src="https://github.com/ansfl/Multiple-MEMS-IMU-Estimation/blob/main/figures/Fig_XSENS_1.jpg?raw=true" width="450" class='center'/>
