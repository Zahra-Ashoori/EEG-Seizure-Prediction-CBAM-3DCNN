# EEG Seizure Prediction using CBAM-3D CNN-LSTM

This repository contains the full pipeline for preprocessing, segmentation, and feature extraction of EEG data for epileptic seizure prediction — based on the paper:

> **"An Epileptic Seizure Prediction Method Based on CBAM-3D CNN-LSTM Model"**  
> [https://doi.org/10.1109/JTEHM.2023.3290036]

---

##  Project Description

The goal of this project is to replicate and enhance a deep learning method for predicting epileptic seizures from EEG data. The original model uses a hybrid CBAM-3D CNN-LSTM architecture applied to time–frequency features generated from scalp EEG signals.

This repo includes:
- EEG preprocessing (band-stop, high-pass filtering, normalization)
- Segmentation of preictal and interictal signals
- Spectrogram generation using STFT
- Training model based on ...
