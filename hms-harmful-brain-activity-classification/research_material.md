# Kaggle Harmful Brain Activity Classification Challenge Links

## Data Exploration and Processing
- **Compact Dataset for Faster Processing**  
  [Brain Spectrograms - Kaggle Dataset](https://www.kaggle.com/datasets/cdeotte/brain-spectrograms)

## Understanding EEG and Spectrograms
- **What is a Spectrogram?**  
  [A Primer on EEG Spectrograms - PubMed Article](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC8901534/)
- **Learning EEG**
  [Learning eeg](https://www.learningeeg.com/montages-and-technical-components)


## Papers and Research
Shane's useful papers Jan 16th:

- You et al., 2020
- https://sci-hub.se/https://www.sciencedirect.com/science/article/abs/pii/S0169260719320000?via%3Dihub
	- from https://www.sciencedirect.com/science/article/abs/pii/S0169260719320000?via%3Dihub
- Summary: 
	- preprocess EEGs to extract time-frequency spectrogram images and train a generative adversarial network (GAN) 
		on the spectrograms that do not contain seizures. 
	- used a 6th or- der Butterworth bandpass filter
	- Converted from EEG trace to spectrogram with the power spectral density (PSD) with the short-time Fourier transform.
		- Constructed the PSD image for each behind-the-ear EEG channel by applying short-time Fourier transform (STFT) for every 32-s window with 50% overlap.
	- For each spectrogram at testing time, they have to search for the latent GAN input that leads to the smallest 
		loss value and use the corresponding generated spectrogram for seizure identification.

- Ilkay et al., 2023
- https://arxiv.org/abs/2301.03470
- Summary:
	- Improvement upon last paper (You et al., 2020)
	- Applied the first fully-unsupervised transformer-based model on raw EEG
	- Their architecture and training objective are particularly designed for multivariate time-series analysis and do not 
		require a sophisticated minimax optimization such as GAN training.
	- The fundamental benefit of a transformer encoder over other DNN architectures is that self-attention can selectively highlight important input features and sequence segments, without relying on sequence-aligned convolutions or slow recurrent modules

*** I'm not sure if it's within the scope of this project to model their transformer and make our own

- Amin et al., 2020
- https://sci-hub.se/https://www.sciencedirect.com/science/article/abs/pii/S1746809419302885
- Summary:
	- 1) Decompose raw EEG trace into approsimations and detail coefficients using DWT (discrete wavelet transform), while discarding non-significant coefficients
	- 2) Converts significant wavelet coefficients to bit streams using atrithmetic coding to compute compression ratio
	- 3) Standardize compression feature set and use ML models to classify seizure or no seizure

- Mehla et al., 2021
- https://sci-hub.se/https://link.springer.com/article/10.1007/s13246-021-00995-3
- Summary: 
	- Authors extract features from raw EEG traces.
	- Use Fourier intrinsic band functions (FIBFs) 
	- 1) EEG signal decomposed into FIBFs
	- 2) Features are extracted from FIBFs and selected relevant features with Krustkal-Wallis test (I've never heard of feature selection with K-W) 
	- 3) Passed on features to SVM classifier.

- Ramos-Aguilar et al., 2020
- https://www.sciencedirect.com/science/article/pii/S0167865520300842
- Summary: 
	- performance depends on the feature extraction phase, where the aim is to find relevant patterns related to different mental activities.
	- approach to extract features from EEG signals is proposed based on spectrograms: 
		- 1) STFT is applied to EEG to obtain time-frequency representations, where parameters such as window length and type are experimented based on the EEG signal frequency. 
		- 2) Spectral peaks are found to be used as reference in order to obtain descriptors per spectrogram. 
		- 3) Three ways for extracting features from EEG are presented, 
			1) based on frequency and surfaces, 
			2) K-means to extract features and the adaptation of local ternary pattern, 
			3) maximum peaks.

    
## Signal Processing and Tools
- **Signal Processing with Scipy.Signal**  
  [SciPy Signal Processing Documentation](https://docs.scipy.org/doc/scipy/reference/signal.html)
- **EEG Signal Analysis Guide**  
  [EEG Signal Analysis With Python - Medium Article](https://reybahl.medium.com/eeg-signal-analysis-with-python-fdd8b4cbd306)

## Educational Videos and Tutorials
- **ML Methods with EEG Data + Kaggle Competitions**  
  [Triton Neurotech - YouTube](https://youtu.be/AjMdirPPnQQ?si=mbO0NRDsr2zG6jzp)
- **Fourier Transform Applications**  
  [Mike X Cohen - YouTube](https://www.youtube.com/watch?v=xPNoHI9_7Wc&list=PLn0OLiymPak28kNU6D_nkUBebb5LRj3E5&index=2)
- **Wavelets-based Feature Extraction**  
  [Rami Khushaba - YouTube](https://www.youtube.com/watch?v=fxfS0vSAsTA)
- **Morlet Wavelets in Time and Frequency**  
  [Mike X Cohen - YouTube](https://www.youtube.com/watch?v=7ahrcB5HL0k)
- **Exporting and Loading Anaconda Environments**  
  [Better Data Science - YouTube](https://www.youtube.com/watch?v=gx403uIwHsc)
- **EfficientNet and EfficientNetV2: Smaller Models and Faster Training**
  [EfficientNet and EfficientNetV2 - YouTube](https://www.youtube.com/watch?v=qoSKbMbf1Pw)
- **Identifying Audio Problems in the RX Spectrogram**
  [Identifying Audio Problems in the RX Spectrogram - YouTube](https://www.youtube.com/watch?v=UsyRPoCT7Yk)


## Kaggle Notebooks
- **EDA and Domain Journey**  
  [HMS - EDA and Domain Journey - Kaggle Notebook](https://www.kaggle.com/code/mvvppp/hms-eda-and-domain-journey#Domain-info)
- **EEG and Spectrogram Features**  
  [CatBoost Starter - [LB 0.67] - Kaggle Notebook](https://www.kaggle.com/code/cdeotte/catboost-starter-lb-0-67)
  **How to make a spectrogram from EEG data**
  [EEG Spectrogram - Kaggle Notebook](https://www.kaggle.com/code/cdeotte/how-to-make-spectrogram-from-eeg?scriptVersionId=159197813)

## Competition and Evaluation Strategies
- **Kaggle Discussion on Evaluation Metric and Data Handling**  
  [HMS - Harmful Brain Activity Classification - Kaggle](https://www.kaggle.com/competitions/hms-harmful-brain-activity-classification/discussion/467038)
- **EEG Dataset Analysis Tool**  
  [MNE Dataset Documentation](https://mne.tools/stable/documentation/datasets.html)

## Clinical EEG Standards
- **Standardized Critical Care EEG Terminology**  
  [ACNS Standardized EEG Terminology](https://www.acns.org/UserFiles/file/ACNSStandardizedCriticalCareEEGTerminology_rev2021.pdf)
- **Analyzing Neural Time Series Data Book**  
  [Analyzing Neural Time Series Data - PDF](https://cdn.discordapp.com/attachments/1195096636108574782/1195410917928751288/EEG_book.pdf)

## Machine Learning and Deep Learning
- **Hugging Face Transformers**  
  [Hugging Face Transformers Documentation](https://huggingface.co/transformers/)
- **Hugging Face Models**  
  [Hugging Face Models Documentation](https://huggingface.co/models)

- **Shane's exploration of HuggingFace.co**

- Videos that helped me get started
- https://www.youtube.com/watch?v=QEaBAZQCtwE --> long introduction (15min)
- https://www.youtube.com/watch?v=_j7JEDWuqL --> medium introduction (10min)


