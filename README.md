# 🧠 EEG Seizure Prediction using CBAM-3D CNN-LSTM

This repository contains the full pipeline for preprocessing, segmentation, and feature extraction of EEG data for epileptic seizure prediction — based on the paper:

> **"An Epileptic Seizure Prediction Method Based on CBAM-3D CNN-LSTM Model"**  
> [🔗 Paper Link]([https://doi.org/10.1109/JTEHM.2023.3290036]

---

##  Project Description

The goal of this project is to replicate and enhance a deep learning method for predicting epileptic seizures from EEG data. The original model uses a hybrid CBAM-3D CNN-LSTM architecture applied to time–frequency features generated from scalp EEG signals.

This repo includes:
- EEG preprocessing (band-stop, high-pass filtering, normalization)
- Segmentation of preictal and interictal signals
- Spectrogram generation using STFT
- Feeding 3D spectrograms into a deep model based on CBAM-3D CNN-LSTM architecture

## 🧠 Dataset

- Dataset: **CHB-MIT Scalp EEG Database**
- Source: [PhysioNet Link](https://physionet.org/content/chbmit/1.0.0/)
- Subjects used:  
  `chb01`, `chb02`, `chb03`, `chb05`, `chb07`, `chb08`, `chb10`, `chb11`, `chb13`, `chb14`, `chb18`

The dataset contains EEG recordings from 23 pediatric epilepsy patients with annotated seizure events.

---

## 🧪 Preprocessing Steps

> As described in the original paper, the following preprocessing steps are applied:

- **Band-stop filters**:
  - 57–63 Hz and 117–123 Hz → to remove powerline interference and its harmonics
- **High-pass filter**:
  - > 0.5 Hz → to remove DC drift
- **Z-score normalization**:
  - Per channel, after filtering

---

## 🔀 Segmentation Strategy

- **Preictal segments**:
  - From 35 minutes to 5 minutes before seizure onset
- **Interictal segments**:
  - At least 4 hours before or after any seizure
- **Segment length**: 8 seconds  
- **Sliding window**: 4 seconds (i.e., 50% overlap)

Each segment is labeled as either `preictal (1)` or `interictal (0)`.

---

## 📈 Feature Extraction (STFT)

For each EEG segment:
- Short-Time Fourier Transform (STFT) is applied
- Spectrograms are generated and saved (either as `.npy` or `.png`)
- These spectrograms form the input to the deep learning model

---

## 🧠 Model: CBAM-3D CNN-LSTM

> Model architecture as per the original paper (to be implemented):

- **3D CNN** block to extract spatio-temporal features
- **CBAM (Convolutional Block Attention Module)** for channel + spatial attention
- **Bi-directional LSTM** to capture temporal dependencies
- **Softmax** output for binary classification

---
