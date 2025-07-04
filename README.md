# Intelligent Condition-Based Monitoring Using Acoustic Signals for Air Compressors

This project presents an automated fault diagnosis system for reciprocating-type air compressors using acoustic signal processing and machine learning. The system performs fault detection and classification using a robust pipeline involving data acquisition, sensitive sensor positioning, signal pre-processing, advanced feature extraction, feature selection, and multiclass classification (e.g., SVM-based).

## Key Features

- Acoustic signal-based fault detection from a single sensor location.
- Preprocessing pipeline: Filtering, clipping, smoothing, and robust normalization.
- Feature extraction from:
  - Time domain
  - Frequency domain (FFT)
  - Time-frequency domain (Wavelet Packet Transform, Morlet Wavelet, DWT)
  - Advanced transforms (STFT, WVD, DCT, etc.)
- Dimensionality reduction using methods like PCA, mRMR, MI-based selectors, and Bhattacharyya Distance.
- Classification using multiclass SVM with OAO/OAA/DDAG strategies.
- Real-time capable with accuracy greater than 99.5% using only 25 selected features.

---
## Main Libraries

- NumPy  
- SciPy  
- Scikit-learn  
- PyWavelets  
- LibSVM (or use scikit-learn's SVM)  
- Matplotlib / Seaborn  

---

## Getting Started

1. **Data Acquisition**  
   Record 5-second acoustic samples (50 kHz sampling rate) using unidirectional microphones. Place microphones approximately 1.5 cm from the compressor.

2. **Preprocessing**  
   Apply filtering (FIR + Butterworth), clipping (minimum standard deviation window), smoothing (moving average), and robust normalization.

3. **Feature Extraction**  
   Extract 286 basic features and optionally 343 advanced ones using transforms like DWT, WPT, MWT, DCT, STFT, etc.

4. **Feature Selection**  
   Use mRMR, NMIFS, or PCA to reduce dimensionality to approximately 25–50 best features.

5. **Classification**  
   Train multiclass SVM with OAO, OAA, or DDAG. Use RBF kernel and tune parameters C and gamma using grid search.

---

## Results

- Accuracy: Greater than 99.5% with mRMR + SVM (RBF kernel).  
- Training size: 50% of data (2-fold) is sufficient for generalization.  
- Best features: WPT, FFT, MWT, DCT.  
- Computation Time: Approximately 10 seconds per recording (optimized feature set).  

---

## Future Work

- Extend to multiple simultaneous fault detection.  
- Add online learning or adaptive models.  
- Optimize for real-time deployment on embedded systems.  

---

## Citation

If you use this work, please cite the original paper:

> Verma, N.K., Sevakula, R.K., Dixit, S., & Salour, A. (2016). *Intelligent Condition-Based Monitoring Using Acoustic Signals for Air Compressors*. IEEE Transactions on Reliability, 65(1), 291-307.

