# Spectrum-Guided-Model-Merging---Focused-Fusion-on-Informative-Layers
The projects apply Spectrum-Guided Model Merging to Vision (ResNet18) and NLP (BERT) models. By calculating the spectral SNR, advanced merging strategies (e.g., SNR Winner, Spectrum Reset) were tested against the standard average, optimizing joint performance on different tasks (FashionMNIST/KMNIST and SST-2/CoLA/Emotion).

**Authors:** Mariastella Gioia La Rocca, Mia Rodotà  
**Affiliation:** Sapienza University of Rome  
**Date:** January 2026

## 📄 Abstract
This project investigates the efficacy of **Spectral Signal-to-Noise Ratio (SNR)**, derived from **Random Matrix Theory (RMT)**, as a metric for merging deep learning models. 

By analyzing the eigenvalue distributions of weight matrices (via the Marchenko-Pastur Law), we distinguish between informative "signal" and random "noise". We compare traditional weight averaging against advanced spectral strategies—including "Spectrum Base Reset" and "SNR Winner Take All"—across **BERT-based Transformers (NLP)** and **ResNet-18 (Vision)**.

## 📂 Repository Structure

### 1. Vision Experiments (ResNet-18)
* **Notebook:** `notebooks/01_ResNet_Vision_Analysis.ipynb`
* **Description:** Implements Spectrum-Guided Model Merging on Convolutional Neural Networks using **FashionMNIST** and **KMNIST**.
* **Key Analysis:** Examines stability across tasks and visualizes the sensitivity of convolutional layers to different merging thresholds (`snr_lowA`, `snr_lowB`, `snr_max`).

### 2. NLP Experiments (BERT - Emotion & Sentiment)
* **Notebook:** `notebooks/02_BERT_SST2_Emotion.ipynb`
* **Description:** Applies spectral merging to BERT models fine-tuned on **SST-2** (Sentiment Analysis) and **Emotion** datasets.
* **Key Analysis:** Layer-wise SNR comparison between models to identify which layers carry more task-specific information.

### 3. NLP Experiments (BERT - CoLA & Strategies)
* **Notebook:** `notebooks/03_BERT_SST2_CoLA_Strategies.ipynb`
* **Description:** Focuses on structural linguistic tasks using the **CoLA** (Linguistic Acceptability) dataset versus SST-2.
* **Strategies Tested:**
    * *Standard Merge (Baseline)*
    * *Spectrum Base Reset*
    * *SNR Winner Strategy*

## 📊 Key Findings
As detailed in the [Paper](paper/Comparative_Analysis_Merging.pdf):
1.  **Structural tasks (e.g., CoLA)** benefit significantly from aggressive SNR strategies like "Winner Take All".
2.  **Distributed semantic tasks (e.g., SST-2)** are better served by Standard or Weighted merging to preserve subtle information.
3.  **Vision tasks (ResNet)** are highly sensitive; "blind" spectral merging can lead to performance collapse in convolutional layers, requiring smoother transition mechanisms.
