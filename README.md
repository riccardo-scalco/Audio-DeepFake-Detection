# Audio Deepfake Detection

[cite_start]This project was developed for the **Digital Forensics and Biometrics** course at the **University of Padua**. [cite_start]It implements a deep learning model designed to distinguish between authentic ("bonafide") and manipulated ("spoof") audio signals[cite: 21].

## 👥 Authors
* [cite_start]**Riccardo Scalco**[cite: 12]
* [cite_start]**Luca Ferrari**[cite: 12]

## 🎯 Project Objective
[cite_start]The primary goal is the implementation of a robust classification model capable of recognizing audio spoofing attacks[cite: 21]. This technology has critical applications in:
* [cite_start]**Voice Authentication**: Protecting biometric systems from cloning[cite: 23].
* [cite_start]**Digital Forensics**: Verifying the authenticity of audio evidence[cite: 23].
* [cite_start]**Fake News Prevention**: Detecting AI-generated voice clones used for misinformation[cite: 23].

## 📊 Dataset
The model is trained and evaluated on the **ASVspoof2019** dataset, covering both:
* [cite_start]**Logical Access (LA)**: Synthetic speech and voice conversion[cite: 42].
* [cite_start]**Physical Access (PA)**: Replay attacks in various environments[cite: 43].

## 🛠️ Technical Stack
* [cite_start]**Language**: Python[cite: 30].
* [cite_start]**Deep Learning**: PyTorch (torch, torchaudio)[cite: 32].
* [cite_start]**Machine Learning Tools**: Scikit-learn (for metrics and calibration)[cite: 34].
* [cite_start]**Data Visualization**: Matplotlib and Seaborn[cite: 32].
* [cite_start]**Environment**: Kaggle Notebooks[cite: 30].

## 🧬 Project Pipeline
1. [cite_start]**Data Preparation**: Loading and organizing the ASVspoof metadata[cite: 64].
2. [cite_start]**Advanced Augmentation**: Improving robustness through Noise addition, Time-Stretching, Pitch Shifting, and Random Masks (Time/Frequency)[cite: 68, 202, 285, 378, 466, 560].
3. [cite_start]**Feature Extraction**: Computation of Mel Spectrograms as the primary input feature[cite: 70].
4. **Model Architecture (SpoofNet)**:
   * [cite_start]CNN Layers + Residual Blocks for local pattern extraction[cite: 684, 690].
   * [cite_start]Squeeze & Excitation (SE) blocks for channel weighting[cite: 685, 691].
   * [cite_start]**Attention Pooling**: Focusing on the most relevant audio regions[cite: 686, 692].
   * [cite_start]MLP Classifier for the final decision[cite: 693, 696].

## 📈 Performance Results
[cite_start]The model achieved high performance on the test set[cite: 719]:
* [cite_start]**Accuracy**: 95.23% [cite: 719]
* [cite_start]**Precision**: 0.9832 [cite: 719]
* [cite_start]**Recall**: 0.9203 [cite: 719]
* [cite_start]**F1-Score**: 0.9507 [cite: 719]
* [cite_start]**AUC-ROC**: 0.9837 [cite: 719]
* [cite_start]**Equal Error Rate (EER)**: 4.62% [cite: 720]

## 🚀 How to Run
1. [cite_start]Ensure you have the ASVspoof2019 dataset structure in your data directory[cite: 44].
2. Install dependencies: `pip install torch torchaudio matplotlib pandas scikit-learn seaborn`.
3. Open and run the `dfb_project.ipynb` notebook to execute the full pipeline from training to evaluation.
