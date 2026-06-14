# Mineral Identification System using Deep Learning
<div align="center">

# MobileNetV2 Transfer Learning for Mineral Classification
An AI-powered image classification system capable of identifying seven different mineral types using Deep Learning and Computer Vision.

*Final Test Accuracy: 85.42%
</div>

#  Overview
The Mineral Identification System is a deep learning project developed using **TensorFlow/Keras** and **MobileNetV2 Transfer Learning** to automatically classify mineral images into seven different categories.
The project demonstrates how transfer learning can be effectively applied to geological image classification by leveraging a pretrained convolutional neural network and fine-tuning it on a custom mineral dataset.

# Objectives
* Automate mineral identification using AI.
* Reduce dependency on manual classification.
* Build a lightweight and accurate image classifier.
* Demonstrate Transfer Learning for real-world applications.
* Create a reusable model for future deployment.

# Model Architecture
The classifier is based on "MobileNetV2", pretrained on ImageNet.

# Training Strategy

# Phase 1
* Freeze MobileNetV2 backbone
* Train custom classification layers

# Phase 2
* Unfreeze upper layers
* Fine-tune using a lower learning rate

Additional techniques used:
* Data Augmentation
* Early Stopping
* Reduce Learning Rate on Plateau
* Model Checkpointing
* Fine-Tuning

# Dataset
The dataset contains images belonging to "7 mineral categories".

# Classes
* Biotite
* Bornite
* Chrysocolla
* Malachite
* Muscovite
* Pyrite
* Quartz

# Dataset Distribution

| Split      | Images    |
| ---------- | --------- |
| Training   | 3,959     |
| Validation | 954       |
| Testing    | 727       |
| **Total**  | **5,640** |

Dataset Structure:
Mineral_Identification_Project/
│
├── train/
├── val/
└── test/
```

# Data Augmentation

The following augmentations were applied during training:

* Rotation
* Width Shift
* Height Shift
* Shear
* Zoom
* Horizontal Flip
* Vertical Flip
* Brightness Adjustment

These transformations improve model robustness and reduce overfitting.

# Training Configuration

| Parameter         | Value                    |
| ----------------- | ------------------------ |
| Base Model        | MobileNetV2              |
| Image Size        | 224 × 224                |
| Batch Size        | 32                       |
| Optimizer         | Adam                     |
| Loss Function     | Categorical Crossentropy |
| Transfer Learning | Yes                      |
| Fine-Tuning       | Yes                      |
| Early Stopping    | Enabled                  |
| Model Checkpoint  | Enabled                  |

---

# Performance
#Final Test Accuracy

# 85.42%

# Per-Class Performance

| Class       | Precision | Recall | F1 Score |
| ----------- | --------- | ------ | -------- |
| Biotite     | 0.86      | 0.92   | 0.89     |
| Bornite     | 0.77      | 0.41   | 0.54     |
| Chrysocolla | 0.96      | 0.82   | 0.89     |
| Malachite   | 0.97      | 0.95   | 0.96     |
| Muscovite   | 0.67      | 0.63   | 0.65     |
| Pyrite      | 0.81      | 0.98   | 0.89     |
| Quartz      | 0.87      | 0.92   | 0.89     |

# Overall Metrics
* Test Accuracy: 85.42%
* Weighted F1 Score: 0.85
* Macro F1 Score: 0.82

#  Results Analysis

The model performs exceptionally well on:
*  Malachite
*  Pyrite
*  Quartz
*  Biotite
*  Chrysocolla

The main challenge lies in distinguishing:
* Bornite
* Muscovite
because of visual similarities with other mineral classes.
Overall, the model generalizes well and exhibits minimal overfitting.

# Features

* Automatic mineral classification
* MobileNetV2 Transfer Learning
* Fine-Tuning
* Data Augmentation
* Confusion Matrix Generation
* Classification Report
* Training History Visualization
* Single Image Prediction
* Saved Model Checkpoint

---

# Project Structure

```
Mineral_Identification_Project/
│
├── Copy_of_Mineral_identification_sample_1.ipynb
├── best_mineral_model.keras
├── Mineral_Identification_Project.7z
├── confusion_matrix.png
├── training_curves.png
├── train/
├── val/
├── test/
└── README.md

# Installation
Install required dependencies:

```bash
pip install tensorflow numpy matplotlib seaborn scikit-learn
```

# Usage
# Load the trained model

```python
from tensorflow.keras.models import load_model

model = load_model("best_mineral_model.keras")
```

# Predict a new mineral image

```python
predict_mineral("sample_image.jpg")
```


# Continue Training

To continue training from the saved checkpoint:

```python
model.fit(
    train_gen,
    validation_data=val_gen,
    epochs=5
)
```

The model resumes from previously learned weights instead of training from scratch.

# Technologies Used

* Python
* TensorFlow
* Keras
* MobileNetV2
* NumPy
* Matplotlib
* Seaborn
* Scikit-learn
* Google Colab

# Applications

* Geological Research
* Mining Industry
* Mineral Exploration
* Educational Tools
* AI-based Rock Classification
* Computer Vision Research


# Future Improvements

* Expand dataset size
* Improve Bornite classification
* Improve Muscovite classification
* Experiment with EfficientNet architectures
* Hyperparameter optimization
* Deploy as a Flask or Streamlit application
* Convert to TensorFlow Lite for mobile devices

# Author
Shivani Sharma
B.Tech CSE (AI & ML)
K.R. Mangalam University

# License
This project is intended for educational and research purposes.

# Conclusion

The Mineral Identification System successfully demonstrates the application of "Transfer Learning with MobileNetV2" for geological image classification. Achieving a "Test Accuracy of 85.42%", the model provides reliable predictions across seven mineral categories while maintaining computational efficiency. It serves as a strong foundation for future deployment and further research in AI-driven mineral recognition.
