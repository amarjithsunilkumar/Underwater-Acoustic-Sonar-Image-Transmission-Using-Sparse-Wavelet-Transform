# Underwater-Acoustic-Sonar-Image-Transmission-Using-Sparse-Wavelet-Transform
Seminar study on transmitting sonar images underwater using compressed sensing and sparse wavelet transform.

# Underwater Acoustic Sonar Image Transmission Using Sparse Wavelet Transform

## Objective
This is my B.Tech seminar report (Electrical and Electronics Engineering, Mar Athanasius College of Engineering, APJ Abdul Kalam Technological University, December 2022). It studies how sonar images can be transmitted efficiently over the underwater acoustic channel, which is dynamic, sensitive to Doppler shift and limited to a few tens of kHz of bandwidth.

The report reviews a **Human Vision System based Sparse Wavelet Transform** approach combined with **compressed sensing**. It finds a sparse representation of a sonar image that preserves edge information, so the image can be transmitted with less data and better bandwidth utilization.

The seminar is based on published research, mainly: G. Han, J. Cui, Y. Su and X. Fu, "Human Vision System based Sparse Wavelet Transform for Underwater Acoustic Sonar Image Transmission," Global Oceans 2020: Singapore – U.S. Gulf Coast.

**Guide:** Prof. Mohitha Thomas

### Skills Learned

- Compressed sensing theory: sparse representation, measurement and reconstruction.
- Wavelet transforms and 2D wavelet decomposition (LL, LH, HL and HH subbands).
- Image compression techniques and their trade-offs (DCT, wavelet, Daubechies, Bandelet transforms).
- Image quality evaluation with PSNR and SSIM.
- Sonar imaging principles: active and passive sonar.
- Reviewing and summarizing technical research papers, and writing a structured technical report.

## Background

### Sonar Imaging
Sonar sends out sound pulses and converts the returning echoes into digital images, which works even in dark or turbid water where cameras fail. A typical sonar image is a fan-shaped grey-scale image. Sonar systems are either **active** (a projector emits a sound wave and a receiver analyzes the reflection) or **passive** (receivers only pick up noise produced by the target).

### The Problem
Sonar images must be sent through the underwater acoustic channel for analysis, but the channel has severe attenuation, multipath delay and very limited bandwidth, so the images have to be compressed. Existing methods have drawbacks:

- **DCT-based coding** (as in JPEG and H.264): causes block effects after transmission.
- **Wavelet compression:** makes images more tolerant of errors, but the recovered edges are blurry.
- **Daubechies transform with compressed sensing:** preserves edges, but needs the image to be known before implementation.

## Method Reviewed

### 1. Compressed Sensing
If a signal is sparse, it can be recovered with high probability from far fewer measurements than traditional sampling needs. The process has three steps:

1. **Sparse representation:** project the image onto a sparse basis.
2. **Measurement:** multiply by a measurement matrix to obtain a small set of samples.
3. **Reconstruction:** recover the image by solving an optimization problem.

### 2. Enhanced Discrete Wavelet Transform (EDWT)
Edges and boundaries are the most important features for identifying objects in sonar images. Enhancement parameters are applied to the wavelet low-pass and high-pass filters to better represent edges and contrast. Comparing decomposition levels, **level 2** gave higher contrast than level 1 while keeping more detail than level 3, making it the best choice for sonar images.

### 3. Sparse Enhanced Discrete Wavelet Transform (SEDWT)
The EDWT matrix is duplicated and shifted row by row to build a sparse transform matrix (SEDWT) that suits compressed sensing and low-speed underwater transmission.

*Ref 1: Processing Pipeline (Input Image → Sparse Representation → Measurement → Reconstruction → Recovered Image)*
![Image Processing Flow](images/processing-flow.png)

## Key Findings (from the reviewed research)

- The sparse enhanced wavelet transform preserves edge and contrast information of sonar images well.
- At different sampling proportions, it performs better than the normal Daubechies wavelet transform, which means more efficient compression for underwater acoustic communication.
- Performance was judged with **PSNR** (peak signal-to-noise ratio) and **SSIM** (structural similarity).

## Advantages and Challenges of Sonar Imaging

**Advantages:** works in zero-visibility water, is unaffected by radio waves, and supports long-distance underwater communication and depth measurement.

**Challenges:** can affect marine life, has poor directional resolution because of the wide beam, and its performance is affected by reverberation.

## Report

The full seminar report is available in this repository: [`seminar-report.pdf`](seminar-report.pdf)
