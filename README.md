# Automated Deforestation Mapping using Deep Learning (ResUNet)

## Project Overview

This project provides an end-to-end pipeline for detecting deforestation through satellite imagery. Utilizing **Sentinel-2 multispectral data**, the system automatically identifies forest loss using a deep learning–based computer vision approach.

The core of the system is a **Residual U-Net (ResUNet)** architecture. By integrating **skip connections** and **residual blocks**, the model preserves high-resolution spatial features, enabling more effective detection of small-scale deforestation compared to standard segmentation architectures.

---

## Tech Stack and Tools

- **Deep Learning Framework:** TensorFlow, Keras (Functional API)  
- **Satellite Data Source:** Sentinel-2 Level-2A  
- **Processing Technique:** NDVI (Normalized Difference Vegetation Index)  
- **Hardware Acceleration:** Mixed Precision Training (float16) on NVIDIA P100 GPU  
- **Development Environment:** Kaggle / Jupyter Notebooks  

---

## Performance Results

The proposed ResUNet model was evaluated against two industry-standard baselines: **Standard U-Net** and **FCN**.

| Model | Accuracy | Recall (Detection Rate) | IoU (Overlap) |
|------|---------|-------------------------|---------------|
| **ResUNet (Proposed)** | 81.6% | 71.7% | 38.9% |
| Standard U-Net | 75.9% | 51.2% | 28.4% |
| FCN Baseline | 78.1% | 58.4% | 32.1% |

---

## External Data and Model Weights

Due to GitHub file size limitations, large datasets and trained model files are hosted on Kaggle.

### Model Weights
The weights are located in the `/models` directory of the Kaggle output.

- **Trained ResUNet Weights (.keras):** https://www.kaggle.com/code/michaelyosef/ict-deforestation-model-03-model-v3  
- **Baseline Models (FCN & U-Net):** https://www.kaggle.com/code/michaelyosef/ict-deforestation-model-03-model-v3

### Datasets
- **Preprocessed Dataset (NPZ Tiles):**  
  https://www.kaggle.com/datasets/michaelyosef/deforestation-data-4  
- **Original Satellite Dataset:**  
  https://www.kaggle.com/datasets/isaienkov/deforestation-in-ukraine

---

## Repository Structure

- **Preprocessing.ipynb**  
  NDVI calculation, cloud masking, and tiling of raw Sentinel-2 data into 256×256 patches.

- **Main_Research.ipynb**  
  Model training, validation, and generation of ROC and Precision–Recall curves.

- **requirements.txt**  
  List of Python dependencies.

- **.gitignore**  
  Prevents large binary files from being tracked by Git.

---

## Setup and Installation

### Clone the Repository

```bash
git clone https://github.com/your-username/deforestation-detection.git
```
### Install dependencies

```bash
pip install -r requirements.txt
```


