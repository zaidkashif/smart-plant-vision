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

## 🧪 Training Summary

| Metric                | Value               |
| --------------------- | ------------------- |
| 📈 Final Accuracy     | ~71% (Validation)   |
| 🔁 Top-5 Accuracy     | ~90%                |
| 🧠 Total Parameters   | ~8 million          |
| 🌸 Number of Classes  | 102                 |
| 🖼️ Training Samples   | 6149                |
| 🧪 Validation Samples | 1020                |
| 🕐 Total Epochs       | 20                  |
| 💾 Model File Size    | ~35 MB (.h5 format) |

---

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

## 📂 Project Structure

```
smart-plant-vision/
├── app.py                # Streamlit app
├── model/
│   ├── ensemble_finetuned.h5
│   └── labels.json
├── utils/
│   ├── gradcam_utils.py
│   └── predict.py
├── assets/
│   └── demo_interface.png
├── requirements.txt
└── README.md
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

## 🌐 Future Enhancements

- Add class-wise precision and recall
- Real-time webcam predictions
- Convert to a mobile app using TensorFlow Lite
- Integrate IoT-based smart plant monitoring (Phase 2)

---

## 🙌 Contributors

**Dr. Adeel Ashraf Cheema**  
Assistant Professor, FAST-NUCES  
AI Researcher | Educator | Project Mentor  
🌐 [LinkedIn Profile](https://www.linkedin.com/in/adeelcheema/)

---

## 📢 Let's Connect

If you’re a student, researcher, or developer exploring Deep Learning or Computer Vision, connect with me:

📫 Email: adeelashrafcheema@fast.edu.pk  
💬 LinkedIn: [Dr. Adeel Ashraf Cheema](https://www.linkedin.com/in/adeelcheema/)

---
