# 🐱🐶 Cats vs Dogs Image Classification using MobileNetV2 (Transfer Learning)

## 📌 Project Overview

This project classifies images as **Cat** or **Dog** using **Transfer Learning** with MobileNetV2. Instead of training a deep neural network from scratch, a pretrained MobileNetV2 model (trained on ImageNet) is used as a feature extractor and then fine-tuned for binary image classification.

---

## 🚀 Features

* Transfer Learning with MobileNetV2
* Binary Image Classification
* Image Preprocessing using `preprocess_input()`
* TensorFlow & Keras
* Model Saving and Loading
* Prediction on New Images
* High Validation Accuracy

---

## 🛠️ Technologies Used

* Python
* TensorFlow
* Keras
* NumPy
* Matplotlib
* MobileNetV2
* Kaggle Notebook

---

## 📂 Dataset

**Cats vs Dogs Sample Dataset**

Dataset Structure:

```
train/
├── cats/
└── dogs/

valid/
├── cats/
└── dogs/
```

Training Images:

* Cats: 1000
* Dogs: 1000

Validation Images:

* Cats: 1002
* Dogs: 998

---

## 🧠 Model Architecture

```
Input Image (224×224×3)
        │
        ▼
preprocess_input()
        │
        ▼
MobileNetV2 (Pretrained on ImageNet)
        │
        ▼
GlobalAveragePooling2D
        │
        ▼
Dense (128, ReLU)
        │
        ▼
Dense (1, Sigmoid)
        │
        ▼
Prediction (Cat / Dog)
```

---

## 📊 Final Results

| Metric              |      Value |
| ------------------- | ---------: |
| Training Accuracy   |    100.00% |
| Validation Accuracy | **98.40%** |
| Validation Loss     | **0.0743** |

---

## 💡 Key Learning

During development, the model initially achieved only about **72% validation accuracy**. The issue was that MobileNetV2 requires its own preprocessing function.

Using:

```python
from tensorflow.keras.applications.mobilenet_v2 import preprocess_input
```

improved validation accuracy dramatically to **98.4%**.

This demonstrates the importance of using the correct preprocessing for pretrained models.

---

## ▶️ How to Run

1. Clone the repository.
2. Install the required libraries.
3. Open the notebook.
4. Train the model or load the saved model.
5. Test the model using your own cat or dog images.

---

## 📁 Repository Structure

```
Cats-vs-Dogs-MobileNetV2/
│
├── Cats_vs_Dogs_MobileNetV2.ipynb
├── cats_vs_dogs_mobilenetv2.keras
├── requirements.txt
├── README.md
└── sample_images/
    ├── cat.jpg
    └── dog.jpg
```

---

## 🎯 Future Improvements

* Fine-tune additional MobileNetV2 layers
* Add Data Augmentation
* Deploy using Streamlit or Flask
* Convert the model to TensorFlow Lite for mobile devices
* Build a web application for real-time image prediction

---

## 👨‍💻 Author

**Mudassar**

This project was developed as part of my Deep Learning and Computer Vision learning journey.
