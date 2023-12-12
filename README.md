# Learning-Based-MEMS-Gyrocompassing

&nbsp; &nbsp;  &nbsp;  &nbsp; &nbsp;  &nbsp;  &nbsp; &nbsp;  &nbsp;  &nbsp; &nbsp;  &nbsp;  &nbsp; &nbsp;  &nbsp;  &nbsp;  <img src="https://github.com/ansfl/MEMS-IMU-Denoising/blob/main/figrues/Logo.png?raw=true" width="500" />

<!-- # MEMS-IMU-Denoising
This repository contains both code and experimental data associated with our paper "Parametric and State Estimation of Stationary MEMS-IMUs: A Tutorial". -->

### Introduction
Inertial navigation systems (INS) are widely used in almost any operational environment, including aviation, marine, and land-based vehicles. Inertial measurements from accelerom- eters and gyroscopes, allow the INS to estimate position, velocity, and orientation of its host vehicle. However due to inherent sensor bias and noise, accuracy is degraded over time, as these error sources propagate into the state estimates, causing them to drift. To mitigate this, different approaches of parametric and state estimation have been proposed, to compensate for undesirable errors, by either frequency-domain filtering, or external information fusion. 

&nbsp;  &nbsp;  &nbsp; &nbsp;  &nbsp; &nbsp; &nbsp; &nbsp;  &nbsp; &nbsp; &nbsp;  &nbsp;  &nbsp; &nbsp;  &nbsp; &nbsp; 
 <img src="https://github.com/ansfl/Multiple-MEMS-IMU-Estimation/blob/main/figures/Fig_Ellipsoid_Medium_B.png?raw=true" width="600" class='center'/>

A candidate solution that is often overlooked is the use of multiple sensors. The increased sampling of the observed phenomenon, results in the improvement of several key factors such as signal accuracy, frequency resolution, noise rejection, and higher redundancy. In this study, a stationary and levelled sensors array is taken, and its robustness against the instrumental errors is simplified and analyzed. Subsequently, the hypothesized model is compared with the experimental results, and the level of agreement between them is thoroughly discussed. Ultimately, our results showcase the vast potential of employing multiple sensors, as we observe improvements spanning from the signal level to each navigation state.

&nbsp;  &nbsp;  &nbsp; &nbsp;  &nbsp; &nbsp; &nbsp; &nbsp;  &nbsp; &nbsp; &nbsp;  &nbsp;  &nbsp; &nbsp;  &nbsp; &nbsp;  <img src="https://github.com/ansfl/Multiple-MEMS-IMU-Estimation/blob/main/figures/PDF_vs_Time_Fin.png?raw=true" width="520" class='center'/>

The main contribution of this work lies in four key aspects: (i) Novel analytical framework - we propose a simplified system model that is error-centred, with a specific focus on the contribution of the sensors count to the INS drift. (ii) Comprehensive validation - we evaluate the effectiveness of our model with an in-lab experiment, followed by a meticulous analysis, visualization, and discussion. (iii) Practicality - all improvements in accuracy and precision, were exclusively tested on real-world applications.

&nbsp; &nbsp; &nbsp;  &nbsp;  &nbsp; &nbsp;  &nbsp; &nbsp; &nbsp; &nbsp;  &nbsp; &nbsp; &nbsp;  &nbsp;  &nbsp; &nbsp;  &nbsp; &nbsp; 
 <img src="https://github.com/ansfl/Multiple-MEMS-IMU-Estimation/blob/main/figures/Fig_combined.png?raw=true" width="520" class='center'/>


### Dataset

The data in this work was obtained from a dedicated apparatus for alignment and synchronization of two arrays of five inertial MEMS-IMUs. 

*"Xsens DOT sensor provides 3D angular velocity using a gyroscope, 3D acceleration using accelerometer and 3D earth magnetic field using a magnetometer. Combined with Xsens sensor fusion algorithms, 3D orientation and free acceleration are provided. With the wireless nature of Bluetooth 5.0, Xsens DOT sensor is an excellent measurement unit for tracking human body motions"* ([Xsense-DOT](https://www.xsens.com/hubfs/Downloads/Manuals/Xsens%20DOT%20User%20Manual.pdf))

&nbsp; &nbsp; &nbsp;  &nbsp;  &nbsp; &nbsp;  &nbsp;  &nbsp; &nbsp;  &nbsp; &nbsp;  &nbsp;  &nbsp; &nbsp;  &nbsp;  &nbsp; &nbsp;  &nbsp;  &nbsp; &nbsp;  &nbsp;  &nbsp; <img src="https://github.com/ansfl/Multiple-MEMS-IMU-Estimation/blob/main/figures/Fig_XSENS_1.jpg?raw=true" width="450" class='center'/>
