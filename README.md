&nbsp; &nbsp;  &nbsp;  &nbsp; &nbsp;  &nbsp;  &nbsp; &nbsp;  &nbsp;  &nbsp; &nbsp;  &nbsp;  &nbsp; &nbsp;  &nbsp;  &nbsp;  <img src="https://github.com/ansfl/MEMS-IMU-Denoising/blob/main/figrues/Logo.png?raw=true" width="500" />

<!-- # MEMS-IMU-Denoising
This repository contains both code and experimental data associated with our paper "Parametric and State Estimation of Stationary MEMS-IMUs: A Tutorial". -->

### Introduction
Inertial navigation systems (INS) are widely used in both manned and autonomous platforms. One of the most critical tasks prior to their operation is to accurately determine their initial alignment while stationary, as it forms the cornerstone for the entire INS operational trajectory. While low-performance accelerometers can easily determine roll and pitch angles (leveling), establishing the heading angle (gyrocompassing) with low-performance gyros proves to be a challenging task without additional sensors. This arises from the limited signal strength of Earth's rotation rate, often overridden by gyro noise itself. Complex missions, marked by inconsistent data availability, can expose the standalone inertial navigation system (INS) to a wide range of instrumental errors that may rapidly degrade the navigation solution. To circumvent this deficiency, in this study we present a practical deep learning framework to effectively compensate for the inherent errors in low-performance gyroscopes. The resulting capability enables gyrocompassing, thereby eliminating the need for subsequent prolonged filtering phase (fine alignment). Through the development of theory and experimental validation, we demonstrate that the improved initial conditions establish a new lower error bound, bringing affordable gyros one step closer to being utilized in high-end tactical tasks.

&nbsp;  &nbsp;  &nbsp; &nbsp;  &nbsp; &nbsp; &nbsp; &nbsp;  &nbsp; &nbsp; &nbsp;  &nbsp;  &nbsp; &nbsp;  &nbsp; &nbsp; 
 <img src="https://github.com/ansfl/Learning-Based-MEMS-Gyrocompassing/blob/main/figures/Fig_measurement.png?raw=true" width="600" class='center'/>

A candidate solution that is often overlooked is the use of multiple sensors. The increased sampling of the observed phenomenon, results in the improvement of several key factors such as signal accuracy, frequency resolution, noise rejection, and higher redundancy. In this study, a stationary and levelled sensors array is taken, and its robustness against the instrumental errors is simplified and analyzed. Subsequently, the hypothesized model is compared with the experimental results, and the level of agreement between them is thoroughly discussed. Ultimately, our results showcase the vast potential of employing multiple sensors, as we observe improvements spanning from the signal level to each navigation state.

&nbsp;  &nbsp;  &nbsp; &nbsp;  &nbsp; &nbsp; &nbsp; &nbsp;  &nbsp; &nbsp; &nbsp;  &nbsp;  &nbsp; &nbsp;  &nbsp; &nbsp;  <img src="https://github.com/ansfl/Multiple-MEMS-IMU-Estimation/blob/main/figures/PDF_vs_Time_Fin.png?raw=true" width="520" class='center'/>

The main contribution of this work lies in four key aspects: (i) Novel analytical framework - we propose a simplified system model that is error-centred, with a specific focus on the contribution of the sensors count to the INS drift. (ii) Comprehensive validation - we evaluate the effectiveness of our model with an in-lab experiment, followed by a meticulous analysis, visualization, and discussion. (iii) Practicality - all improvements in accuracy and precision, were exclusively tested on real-world applications.

&nbsp; &nbsp; &nbsp;  &nbsp;  &nbsp; &nbsp;  &nbsp; &nbsp; &nbsp; &nbsp;  &nbsp; &nbsp; &nbsp;  &nbsp;  &nbsp; &nbsp;  &nbsp; &nbsp; 
 <img src="https://github.com/ansfl/Multiple-MEMS-IMU-Estimation/blob/main/figures/Fig_combined.png?raw=true" width="520" class='center'/>


### Dataset

The data in this work was obtained from a dedicated apparatus for alignment and synchronization of two arrays of five inertial MEMS-IMUs. 

*"Xsens DOT sensor provides 3D angular velocity using a gyroscope, 3D acceleration using accelerometer and 3D earth magnetic field using a magnetometer. Combined with Xsens sensor fusion algorithms, 3D orientation and free acceleration are provided. With the wireless nature of Bluetooth 5.0, Xsens DOT sensor is an excellent measurement unit for tracking human body motions"* ([Xsense-DOT](https://www.xsens.com/hubfs/Downloads/Manuals/Xsens%20DOT%20User%20Manual.pdf))

&nbsp; &nbsp; &nbsp;  &nbsp;  &nbsp; &nbsp;  &nbsp;  &nbsp; &nbsp;  &nbsp; &nbsp;  &nbsp;  &nbsp; &nbsp;  &nbsp;  &nbsp; &nbsp;  &nbsp;  &nbsp; &nbsp;  &nbsp;  &nbsp; <img src="https://github.com/ansfl/Multiple-MEMS-IMU-Estimation/blob/main/figures/Fig_XSENS_1.jpg?raw=true" width="450" class='center'/>
