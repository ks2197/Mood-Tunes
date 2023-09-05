
# Mood BrainConnect

This repository comprises the code for emotion recognition, which utilizes wavelet transform and SVM classifiers with an RBF kernel.


## Abstract:
This project aims to propose emotion recognition using electroencephalography (EEG) techniques.​ ​An electroencephalogram (EEG) is a machine that detects electrical activity in a human brain using small metal discs (electrodes) attached to the scalp. The brain cells communicate via electrical impulses and are active all the time, even when we are asleep. This activity shows up as wavy lines on an EEG recording.
## Dataset Summary:
The data set contains downsampled signal, preprocessed and segmented versions of the EEG data in Matlab (.mat file). The data was downsampled to 200Hz. A bandpass frequency filter from 0-75Hz was applied. EEG segments were extracted according to the duration of clips. There are a total of 45 .mat (Matlab) files, one for each experiment. Each subject performed the experiment three times with an interval of about one week. Each subject file contains 16 arrays. 15 arrays contain segmented preprocessed EEG data of 15 trials in one experiment (eeg_1~eeg_15, channel×data). An array named ‘labels’ contains the label of the corresponding emotional labels (-1 for negative, 0 for neutral and +1 for positive). The detailed order of the channels is included in the dataset.
##  Steps Involved:
Preprocessing: The initial step involves data preprocessing, where we apply a filtering process to the EEG data, restricting it to the 0-75Hz frequency range. This results in a new matrix with a 200Hz sampling frequency. We employ a Finite Impulse Response 'Low pass filter,' with a filter order of 5 (or 10 if needed), to ensure data stability after processing. 



Feature Extraction: Subsequently, we move to feature extraction. In this phase, we dissect the preprocessed EEG input into five distinct frequency sub-bands utilizing the powerful technique of wavelet filter banks. These filter banks enable the isolation of various EEG signal types, including alpha, beta, gamma, delta, and theta waves. This separation is achieved through an iterative process of applying filters, yielding high-pass (detail coefficient) and low-pass (approximation coefficient) components. This iterative process is repeated for each channel, resulting in the extraction of entropy and energy features for each sub-band, resulting in a total of 10 features per channel and a comprehensive 620 features for each preprocessed EEG signal.

Entropy: Entropy measurement is a vital aspect of our approach, as it quantifies the level of uncertainty within the EEG signals. This measurement reflects the potential configurations or predictability of the signals, a crucial component in emotion recognition.

Energy: Wavelet energy analysis complements our feature extraction process. It provides insights into the distribution of principal lines, wrinkles, and ridges across various resolutions or scales within the EEG data, further enhancing our understanding of emotional states.

Feature Reduction: To manage the dimensionality of the extracted features, we employ Principal Component Analysis (PCA). PCA is a fundamental technique that transforms correlated features into uncorrelated principal components (PCs) through singular value decomposition. This process involves mean normalization, covariance matrix computation, eigenvalue and eigenvector derivation, and ultimately, the extraction of reduced features or principal components (PCs).

Classification: In the final phase, we employ the PCs obtained from the feature reduction step as input for a Support Vector Machine (SVM) classifier. This classifier plays a pivotal role in predicting emotional states based on the transformed EEG features, ultimately providing a valuable tool for emotion recognition.

This project's success is indebted to the following key components:


Wavelet Transform: 
  Utilized for precise frequency analysis and feature extraction.
Principal Components Analysis: Employed for feature dimensionality reduction.
Support Vector Machines: Essential for classifying emotional states.

Seed Dataset: The foundational data source that enabled our research to thrive.


Note: Dataset was taken from SEED Dataset





