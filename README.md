# 🌿 Smart Plant Vision

**Smart Plant Vision** is a Deep Learning-based image classification project designed to identify flowers and plants using an ensemble of fine-tuned CNNs. This project was built as a hands-on learning journey and demonstrates modern techniques in transfer learning, feature fusion, and interpretability via Grad-CAM, all wrapped in a clean Streamlit interface.

---

## 🚀 Project Journey

I started by exploring the **Oxford Flowers 102** dataset and implemented a basic CNN from scratch. After limited performance, I switched to transfer learning with **MobileNetV2**, then experimented with **ResNet50**, and finally fused both models for feature extraction to build a powerful **Ensemble CNN** architecture. Then:

- Fine-tuned the ensemble model with CosineDecay learning rate scheduling
- Used label smoothing to improve generalization
- Evaluated performance with Top-1 and Top-5 accuracy
- Visualized misclassifications and model confusion
- Built and deployed a user-friendly **Streamlit app** interface
- Integrated **Grad-CAM** visualizations to make predictions interpretable
- Documented the project with a LinkedIn-ready summary and README

---

## 🔍 Features

- ✅ Upload any flower image for prediction
- 🔁 Feature Fusion from **MobileNetV2** and **ResNet50**
- 🎯 Top-5 class prediction probabilities
- 📊 Training summary and model metrics
- 🔥 Grad-CAM visualization (highlight model focus areas)
- 🖥️ Streamlit-based interactive interface

---

## 🧠 Model Architecture

- Feature extractors: Pretrained **MobileNetV2** and **ResNet50**
- Concatenated features passed through dense layers
- Dropout for regularization
- Final output: 102-class softmax
- Optimizer: **Adam** with **CosineDecay**
- Loss: **CategoricalCrossentropy** with label smoothing
- Metrics: Accuracy + Top-5 Categorical Accuracy

---

 ## 🔨 Project Pipeline

1. Preprocessing
   Loaded .mat files for label and split information.

Resized images to 224x224 and normalized pixel values.

Created NumPy arrays: X_train, X_valid, X_test.

2. Baseline Model: CNN from Scratch
   3 Conv2D layers + BatchNorm + Dropout

Poor generalization on validation data

Served as baseline for comparison

3. Transfer Learning with MobileNetV2
   Loaded pretrained weights (imagenet)

Added custom dense and softmax layers

Initial training (frozen) followed by fine-tuning

Achieved 71% validation accuracy after tuning

4. Ensemble Feature Fusion (MobileNetV2 + ResNet50)
   Extracted features from both models

Concatenated embeddings before Dense layers

Fine-tuned last 120 layers of both networks

Used:

CosineDecay scheduler

Label Smoothing (CategoricalCrossentropy with label_smoothing=0.1)

TopK Categorical Accuracy (Top-5)

EarlyStopping, ReduceLROnPlateau, ModelCheckpoint

## 📊 Evaluation & Insights
Plotted training/validation accuracy and loss

Evaluated confusion matrix and classification report

Misclassifications visualized

Top-5 predictions displayed in the Streamlit UI

Grad-CAM added for visual explanation

🧠 Architecture: Feature Fusion
Two branches: MobileNetV2 and ResNet50 (truncated after global_avg_pool)

Features concatenated

Dense → Dropout → Output layer

Fine-tuned on top 120 layers of both models

## 📦 How to Run

Install dependencies:

```bash
pip install -r requirements.txt
```

Run the app:

```bash
streamlit run app.py
```

---

## 🎯 Dataset Details

- **Oxford Flowers 102** from the VGG group
- Total Images: 8189
- Classes: 102 flower categories
- Data split: Train (6149), Valid (1020), Test (1020)

---

## 🔥 Grad-CAM Visualization

Visualize **where** the model focuses while making predictions.

![Grad-CAM Demo](./assets/gradcam_sample.png)

---
