# Chest X-Ray Classification for Medical Diagnosis

**[English](README.md)** | [Русский](README.ru.md)

---

## Project Topic

Development of a web application for physicians that automatically analyzes chest X-ray images and provides preliminary diagnoses using deep learning methods.
The project is based on the open [VinBigData Chest X-ray](https://www.kaggle.com/competitions/vinbigdata-chest-xray-abnormalities-detection/data) dataset.

Goal: Assist physicians in preliminary image analysis and reduce workload during initial diagnostics.

---

## Team Members

- Anna Sorokina
- Mark Makhmudov
- Ekaterina Burova
- Artem Kargopolov

---

## Project Supervisor

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Gleb Bulygin

---

## Annual Work Plan

1. Data collection and preprocessing, conducting EDA, exploring distributions and labels
2. Studying existing approaches and implementing a baseline model using classical ML methods
3. Creating a simple web service with implementation of the best ML solution to demonstrate functionality
4. Experiments with DL architectures: exploring and comparing various neural network approaches (ResNet, DenseNet, EfficientNet)
5. Selecting and fine-tuning the best DL architecture, applying augmentation and regularization techniques
6. Refining the web application: integrating the improved DL model, enhancing UI and functionality based on feedback

---

## Tech Stack

- Python
- PyTorch, Torchvision
- Pandas, NumPy
- Matplotlib, Seaborn
- scikit-learn
- scikit-image (for LBP and HOG feature extraction)
- FastAPI, Streamlit
- Docker, Git
- uv

---

## Setup for Contributors

### Prerequisites

- Python 3.10 or higher
- [uv](https://github.com/astral-sh/uv)

Install `uv`:
```bash
curl -LsSf https://astral.sh/uv/install.sh | sh
```

### Initial Setup

After cloning the repository:

```bash
make install
```

### Development Workflow

**Format code:**
```bash
make format
```
Formats all Python files and Jupyter notebooks with black and isort.

**Lint code:**
```bash
make lint
```
Runs type checking (pyright) and linting (flake8) on all code and notebooks.

## Dataset

Source: [VinBigData Chest X-ray](https://www.kaggle.com/competitions/vinbigdata-chest-xray-abnormalities-detection/data)
Contains over 18,000 chest X-ray images with annotations for 15 types of diseases.

---

## ML Baseline

### Feature Extraction

1. Local Binary Patterns (LBP) - texture features
   Encodes local textures based on comparing pixel intensities with their neighbors.
   Useful for analyzing lung tissue, shadows, and opacities.

2. Histogram of Oriented Gradients (HOG) - edge features
   Describes shapes and gradient directions.
   Applicable for detecting contours of lungs, heart, and pathological areas.

---

### Classical ML Models

To classify the extracted features, we plan to test several standard algorithms:

- RandomForestClassifier
- XGBoost
- SVM
- LogisticRegression (as a control model)
