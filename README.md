# Facial Recognition Colab 

<div align="center">

![TensorFlow](https://img.shields.io/badge/TensorFlow-2.15-FF6F00?style=for-the-badge&logo=tensorflow&logoColor=white)
![Keras](https://img.shields.io/badge/Keras-3.0-D00000?style=for-the-badge&logo=keras&logoColor=white)
![Python](https://img.shields.io/badge/Python-3.12-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Google Colab](https://img.shields.io/badge/Google_Colab-F9AB00?style=for-the-badge&logo=googlecolab&logoColor=white)
![MobileNetV2](https://img.shields.io/badge/MobileNetV2-Transfer_Learning-009688?style=for-the-badge)

**An AI-powered Facial Recognition system built with Transfer Learning (MobileNetV2) on Google Colab.**

</div>

---

##  Overview
This project implements a **Deep Learning-based Facial Recognition** system capable of identifying **35 unique individuals** from selfie images. The model leverages **Transfer Learning** with Google's pre-trained **MobileNetV2** architecture, combined with custom classification layers and **Data Augmentation** techniques to achieve high accuracy even with limited training data (~60 images per person).

##  Problem Statement
Given a selfie image of a person, the AI must correctly identify **who** that person is out of 35 known individuals. The system is designed to work in real-time with an interactive upload interface.

## 📊 Dataset
- **Source**: Selfie images collected from 35 individuals.
- **Volume**: ~60 images per person (~2,100 total images).
- **Split**: 80% Training / 20% Validation.
- **Storage**: Google Drive (shared folder with shortcut).

> **Note**: The raw image dataset is not included in this repository due to privacy and size constraints.

## Model Architecture

| Layer | Description |
|-------|-------------|
| **Data Augmentation** | `RandomFlip`, `RandomRotation(0.1)`, `RandomZoom(0.2)` |
| **Preprocessing** | Rescaling pixel values to `[-1, 1]` for MobileNetV2 |
| **Feature Extractor** | MobileNetV2 (pre-trained on ImageNet, frozen weights) |
| **Pooling** | GlobalAveragePooling2D |
| **Regularization** | Dropout (rate = 0.3) |
| **Classification Head** | Dense layer with Softmax activation (35 classes) |

### Why MobileNetV2?
- Pre-trained on **millions of images** (ImageNet) — already understands facial features like eyes, nose, mouth.
- **Lightweight & fast** — ideal for real-time inference on Colab.
- **Transfer Learning** allows high accuracy even with small datasets (~60 images/person).

##  Features
- **Transfer Learning with MobileNetV2**: Leverages Google's powerful pre-trained model for superior feature extraction.
- **Data Augmentation**: Dynamically generates new training samples via random flips, rotations, and zooms to prevent overfitting.
- **Smart Data Pipeline**: Implements `cache()` and `prefetch()` for 10x faster data loading from Google Drive.
- **Interactive Upload Widget**: Built-in Jupyter widget for real-time image upload and instant face prediction.
- **Training Visualization**: Plots Accuracy and Loss curves across all training epochs.

## 💻 How to Use

### Prerequisites
- A Google account with access to Google Colab.
- The selfie dataset uploaded to Google Drive.

### Quick Start
1. Upload `Facial_Recognition_Colab.ipynb` to your Google Drive.
2. Open the notebook with **Google Colab**.
3. Go to **Runtime → Change runtime type → T4 GPU**.
4. Click **Run All** and wait for all cells to complete:
   - **Cell 1**: Mounts Google Drive.
   - **Cell 1.5**: Copies dataset to Colab's local SSD for faster I/O.
   - **Cell 2**: Loads and preprocesses the image dataset.
   - **Cell 3**: Builds the MobileNetV2-based model.
   - **Cell 4**: Trains the model for 25 epochs.
   - **Cell 5**: Plots training/validation accuracy and loss curves.
   - **Cell 6**: Launches the interactive upload widget for testing.
5. Scroll to the bottom and upload a selfie to test the AI!

##  Training Results
The model typically achieves:
- **Training Accuracy**: ~95–99%
- **Validation Accuracy**: ~85–95%
- **Training Time**: ~5–10 minutes on T4 GPU

##  Project Structure
```
Facial_Recognition_Colab/
├── Facial_Recognition_Colab.ipynb   # Main notebook (run on Colab)
├── README.md                        # Project documentation
└── .gitignore                       # Git ignore rules
```

##  Tech Stack
- **Deep Learning Framework**: TensorFlow / Keras
- **Base Model**: MobileNetV2 (ImageNet weights)
- **Training Environment**: Google Colab (T4 GPU)
- **Data Storage**: Google Drive
- **Language**: Python 3.12

##  Contributing
Contributions, issues, and feature requests are welcome! Feel free to check the [issues page](https://github.com/DevOpsLogistics/Facial_Recognition_Colab/issues).

##  License
This project is open source and available under the [MIT License](LICENSE).

---
<div align="center">
  <i>Built with for AI-powered Facial Recognition.</i>
</div>
