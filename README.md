&nbsp; &nbsp;  &nbsp;  &nbsp; &nbsp;  &nbsp;  &nbsp; &nbsp;  &nbsp;  &nbsp; &nbsp;  &nbsp;  &nbsp; &nbsp;  &nbsp;  &nbsp;  <img src="https://github.com/ansfl/MEMS-IMU-Denoising/blob/main/figrues/Logo.png?raw=true" width="500" />


### Introduction
Inertial navigation systems (INS) are widely used in both manned and autonomous platforms. One of the most critical tasks prior to their operation is to accurately determine their initial alignment while stationary, as it forms the cornerstone for the entire INS operational trajectory. While low-performance accelerometers can easily determine roll and pitch angles (leveling), establishing the heading angle (gyrocompassing) with low-performance gyros proves to be a challenging task without additional sensors. While in stationary conditions, each measurement was recorded at a sampling rate of 600 Hz for 4 minutes, maintaining an average interval of 5$ ^\circ$ across the entire 360$ ^\circ$ azimuth plane. The overall dataset comprises 80 samples, randomly split into training, validation, and test sets with a ratio of 70:10:20, where training was conducted using a single Nvidia T4 GPU. 

&nbsp;  &nbsp;  &nbsp; &nbsp;  &nbsp; &nbsp; &nbsp; &nbsp;  &nbsp; &nbsp; &nbsp;  &nbsp;  &nbsp; &nbsp;  &nbsp; &nbsp; 
 <img src="https://github.com/ansfl/Learning-Based-MEMS-Gyrocompassing/blob/main/figures/Fig_measurement.png?raw=true" width="600" class='center'/>

The figure above provides a representative visualization of a random gyroscope sample lasting 4-minute across all three 3 channels, resulting in a dimensionality of 144,000$\times$3. While the dense measurements form the colored background for each axis, their corresponding sample means are marked with dashed lines to emphasize the specific axial projection of $\omega_{ie}$. To examine the instrumental noise under steady-state conditions, a 1-hour static measurement is recorded, and the well-known Allan Variance (AV) analysis is then performed to quantify error dynamics through extensive time averaging:

&nbsp;  &nbsp;  &nbsp; &nbsp;  &nbsp; &nbsp; &nbsp; &nbsp;  &nbsp; &nbsp; &nbsp;  &nbsp;  &nbsp; &nbsp;  &nbsp; &nbsp; 
 <img src="https://github.com/ansfl/Learning-Based-MEMS-Gyrocompassing/blob/main/figures/Fig_AV.png?raw=true" width="700" class='center'/>

Next, the stabilization process of the baseline signal can be illustrated, accompanied by the running version of a one standard deviation ($\pm \sigma(n)$). The top subfigure presents the short-term time scale, while the bottom one shows the asymptotic convergence resulting from the long-lasting averaging attributes. This demonstrates how the inclusion of additional collected samples effectively cancels out the noise effects.

 &nbsp;  &nbsp;  &nbsp; &nbsp;  &nbsp; &nbsp; &nbsp; &nbsp;  &nbsp; &nbsp; &nbsp;  &nbsp;  &nbsp; &nbsp;  &nbsp; &nbsp; 
 <img src="https://github.com/ansfl/Learning-Based-MEMS-Gyrocompassing/blob/main/figures/fig_w_ie.png?raw=true" width="700" class='center'/>

And finally, after training the model' or alternatively, using the pre-trained weights, performances of both the baseline (blue bubbles) and our model (yellow triangles), can be compared with respect to the GT heading angle of $\psi_{\,\text{GT}}=192.1 ^\circ$, is provided for reference in green.

 &nbsp;  &nbsp;  &nbsp; &nbsp;  &nbsp; &nbsp; &nbsp; &nbsp;  &nbsp; &nbsp; &nbsp;  &nbsp;  &nbsp; &nbsp;  &nbsp; &nbsp; 
 <img src="https://github.com/ansfl/Learning-Based-MEMS-Gyrocompassing/blob/main/figures/Fig_GC_ML.png?raw=true" width="500" class='center'/>


In conclusion, this study we present a practical deep learning framework to effectively compensate for the inherent errors in low-performance gyroscopes. By learning its temporal and spatial error patterns, our model demonstrates robustness to internal and environmental disturbances, allowing for accurate gyrocompassing within shorter time intervals. Our main contribution lies in three key aspects.

### Experimental setup & Dataset

To ensure robust generalizability, acquiring data of both quantity and quality is crucial. The figure below illustrates our experimental setup conducted under controlled laboratory conditions, free from external disturbances. The five main components are highlighted in blue parentheses:

1) Control module\footnote{MRU-P datasheet @ [https://www.inertiallabs.com/mru-datasheet]: Ensures level conditions and
   provides GT heading angles ($y$) with a static accuracy of $0.2^\circ$.
2) Test module\footnote{Emcore SDC500 datasheet @ [https://emcore.com/SDC500.pdf](https://emcore.com/wp-content/uploads/2022/05/966762_B-SDC500.pdf). Positioned at the opposite end of the diameter, our MEMS-IMU provides stationary measurements ($x_0, ..., x_t$) at an opposing heading angle ($y-180^\circ$), with specified BI of 1$^\circ$/hr and ARW of 0.02$^\circ$/$\sqrt{\text{hr}}$.
3) Rotating plate: Both sensors are positioned on a levelled plate that rotates freely around its azimuth axis, allowing stationary measurements across various heading angles.
4) Power supply: Ensures a stable and reliable source of energy for uninterrupted system functionality.
5) Computing unit: Serves as the central processing hub, facilitating efficient operation and ensuring that real-time data is saved, labeled, and appropriately organized.

&nbsp;  &nbsp;  &nbsp; &nbsp;  &nbsp; &nbsp; &nbsp; &nbsp;  &nbsp; &nbsp; &nbsp;  &nbsp;  &nbsp; &nbsp;  &nbsp; &nbsp; 
 <img src="https://github.com/ansfl/Learning-Based-MEMS-Gyrocompassing/blob/main/figures/Fig_Setup.jpg?raw=true" width="600" class='center'/>


## Code

For convenience, both inference and training notebooks are provided, GPU-required.

* **Full Mode** - Full solution pipeline from training to inference. 

* **Test Mode** - Direct inference and comparison between competing models, by uploading pretrained model weights, trained over *single Nvidia T4 GPU*. 

### Directory tree
<pre>
[root directory]
├── figures
├── data
├── execution
|   ├── Training Mode
|       └── *Training.ipynb*
|   └── Inference Mode
|       ├── *Inference.ipynb*
|       ├── RNN.pt
|       ├── Bi_LSTM.pt
|       └── Bi_GRU.pt
...
└── requirements.txt
<!--  Readme.md -->
</pre>


## Citation

Would appreciate the users stars (on this repo) and citation of our article as:
```
@article{shurin2022autonomous,
  title={Learning-based-Gyrocompassing},
  author={Engelsman, Daniel, and, Klein, Itzik},
  journal={ArXiv},
  pages={10191--10201},
  year={2023}
}
```

[<img src=https://upload.wikimedia.org/wikipedia/commons/thumb/a/a8/ArXiv_web.svg/250px-ArXiv_web.svg.png width=70/>](https://arxiv.org/abs/2206.05937)
