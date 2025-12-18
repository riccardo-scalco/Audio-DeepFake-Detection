# Audio Deepfake Detection

This project was developed for the **Digital Forensics and Biometrics** course at the **University of Padua**. It implements a deep learning model designed to distinguish between authentic ("bonafide") and manipulated ("spoof") audio signals.

## 👥 Authors
* **Riccardo Scalco** 
* **Luca Ferrari** 

## 🎯 Project Objective
The primary goal is the implementation of a robust classification model capable of recognizing audio spoofing attacks. This technology has critical applications in:
* **Voice Authentication**: Protecting biometric systems from cloning.
* **Digital Forensics**: Verifying the authenticity of audio evidence.
* **Fake News Prevention**: Detecting AI-generated voice clones used for misinformation.

## 📊 Dataset
The model is trained and evaluated on the **ASVspoof2019** dataset, covering both:
* **Logical Access (LA)**: Synthetic speech and voice conversion.
* **Physical Access (PA)**: Replay attacks in various environments.

## 🛠️ Technical Stack
* **Language**: Python.
* **Deep Learning**: PyTorch (torch, torchaudio).
* **Machine Learning Tools**: Scikit-learn (for metrics and calibration analysis).
* **Data Visualization**: Matplotlib and Seaborn.
* **Environment**: Kaggle Notebooks.

## 🧬 Project Pipeline
1. **Data Preparation**: Loading and organizing the ASVspoof metadata and flac files.
2. **Advanced Augmentation**: Improving robustness through Noise addition, Time-Stretching, Pitch Shifting, and Random Masks (Time/Frequency).
3. **Feature Extraction**: Computation of Mel Spectrograms (80 bands) as the primary input feature.
4. **Model Architecture (SpoofNet)**:
   * CNN Layers + Residual Blocks for local pattern extraction.
   * Squeeze & Excitation (SE) blocks for channel-wise weighting.
   * **Attention Pooling**: Focusing on the most relevant audio regions.
   * MLP Classifier for the final decision.

## 📈 Performance Results
The model achieved high performance on the test set:
* **Accuracy**: 95.23%
* **Precision**: 0.9832
* **Recall**: 0.9203
* **F1-Score**: 0.9507
* **AUC-ROC**: 0.9837
* **Equal Error Rate (EER)**: 4.62%

## 🚀 How to Run
1. Ensure you have the ASVspoof2019 dataset structure in your data directory.
2. Install dependencies: `pip install torch torchaudio matplotlib pandas scikit-learn seaborn tqdm`.
3. Open and run the `dfb_project.ipynb` notebook to execute the full pipeline from data preparation to evaluation.
