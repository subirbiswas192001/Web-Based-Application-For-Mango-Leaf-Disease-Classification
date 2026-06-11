# 🌿 MangiferaNet — Mango Leaf Disease Classifier

<p align="center">
  <img src="https://img.shields.io/badge/Python-3.12-blue?style=for-the-badge&logo=python"/>
  <img src="https://img.shields.io/badge/TensorFlow-2.20.0-orange?style=for-the-badge&logo=tensorflow"/>
  <img src="https://img.shields.io/badge/Keras-3.13.2-red?style=for-the-badge&logo=keras"/>
  <img src="https://img.shields.io/badge/Flask-3.0.0-black?style=for-the-badge&logo=flask"/>
  <img src="https://img.shields.io/badge/Accuracy-99%25-brightgreen?style=for-the-badge"/>
</p>

<p align="center">
  <b>A Lightweight and Intelligent Web-Based Framework for Automated Detection of Mango Leaf Diseases</b><br/>
  Based on MobileNetV2 Architecture | 99% Classification Accuracy | 8 Disease Classes
</p>

---

## 📄 Research Paper

> **MangiferaNet: A Survey-Driven Explainable Lightweight Deep Learning Framework for Automated Mango Leaf Disease Detection and Web-Based Diagnosis**

This repository contains the full implementation of the MangiferaNet framework, as described in the research paper. The model is deployed as a user-friendly web application, enabling farmers and agricultural stakeholders to perform real-time mango leaf disease diagnosis.

---

## 🔍 Overview

Mango leaf diseases pose a significant challenge to agricultural productivity, particularly in regions where mango cultivation is a cornerstone of the economy. **MangiferaNet** addresses this by providing:

- ✅ Automated disease detection using deep learning
- ✅ 99% classification accuracy on two dataset namely MLDID (3000) and MLD24 (6400) images
- ✅ Real-time diagnosis via a web-based interface
- ✅ Lightweight MobileNetV2 architecture for efficient inference

---

## 🏷️ Disease Classes

The model classifies mango leaves into **8 categories**:

| Class | Disease | Description |
|-------|---------|-------------|
| 0 | **Anthracnose** | Fungal disease causing dark, sunken lesions |
| 1 | **Bacterial Canker** | Bacterial infection with water-soaked lesions |
| 2 | **Die Back** | Branches dying from tip backward |
| 3 | **Gall Midge** | Insect infestation causing gall formation |
| 4 | **Cutting Weevil** | Pest damage on leaf margins |
| 5 | **Powdery Mildew** | White powdery coating on leaf surfaces |
| 6 | **Sooty Mould** | Black fungal growth on leaves |
| 7 | **Healthy** | No disease detected |

---

## 🏗️ Model Architecture

```
Input (224×224×3)
        ↓
MobileNetV2 (pretrained on ImageNet, frozen)
        ↓
Flatten
        ↓
Dense(256, activation='relu')
        ↓
Dropout(0.5)
        ↓
Dense(8, activation='softmax')
        ↓
Output (8 classes)
```

- **Base Model:** MobileNetV2
- **Input Size:** 224 × 224 pixels
- **Optimizer:** RMSprop (lr=0.001)
- **Loss:** Categorical Crossentropy
- **Epochs:** 50
- **Dataset:** 3000 9(4 disease classses + healthy) additionally 6,400 images (7 disease classes + healthy)
- **Accuracy:** 99%

---

## 🚀 Web Application

The model is deployed as a Flask web application with the following features:

- 📤 Drag & drop image upload
- 🔍 Real-time disease prediction
- 📊 Confidence score with animated bar
- 📈 All class probabilities breakdown
- ❌ Irrelevant image detection (non-mango-leaf rejection)
- 📱 Responsive design for mobile & desktop

---

## 📁 Project Structure (This fill will be available after publish paper) 

```
MangiferaNet/
├── app.py                  # Flask backend & prediction logic
├── templates/
│   └── index.html          # Frontend UI
├── static/
│   ├── style.css           # Styling
│   └── script.js           # Frontend logic
├── uploads/                # Temporary uploaded images
├── model.keras             # Trained model (download separately)
├── requirements.txt        # Python dependencies
├── Dockerfile              # Docker configuration for deployment
└── README.md               # Project documentation
```

---

## ⚙️ Installation & Setup

### Prerequisites
- Python 3.12+
- Anaconda (recommended)

### Step 1 — Clone the repository
```bash
git clone https://github.com/subirbiswas192001/MangiferaNet.git
cd MangiferaNet
```

### Step 2 — Create conda environment
```bash
conda create -n mango_app python=3.12
conda activate mango_app
```

### Step 3 — Install dependencies
```bash
pip install -r requirements.txt
```

### Step 4 — Download the model
Download `model.keras` from the link below and place it in the project root:

> 🔗 **[Download model.keras — Hugging Face](https://huggingface.co/spaces/Subir19/mango-leaf-disease-classifier)**

### Step 5 — Run the app
```bash
python app.py
```

### Step 6 — Open in browser
```
http://localhost:7860
```

---

## 🌐 Live Demo

> 🚀 **[Try it live on Hugging Face Spaces](https://huggingface.co/spaces/Subir19/mango-leaf-disease-classifier)**

---

## 📦 Requirements

```
flask==3.0.0
tensorflow==2.20.0
keras==3.13.2
numpy
Pillow
werkzeug==3.0.1
gunicorn
```

---

## 🔬 Research Contributions

1. Development of a CNN-based framework for mango leaf disease classification
2. Validation of the model on a comprehensive, real-world dataset of total 9,400 images
3. Demonstration of superior performance (98% accuracy) compared to state-of-the-art approaches
4. XAI Analysis; Original Image vs Grad-CAM++, Vanilla Gradients, Integrated
Gradients (IG), SmoothGrad visualizations highlighting regions contributing to predic-
tions for selected mango leaf disease classes. Color intensity corresponds to contribution
strength.
5. Deployment of the model in an accessible web application for real-time disease diagnosis

---

## 📊 Results

| Metric | Value |
|--------|-------|
| Classification Accuracy | **99%** |
| Number of Classes | **8** |
| Dataset Size | **Total 9,400 images** |
| Model Architecture | **MobileNetV2** |
| Input Size | **224 × 224** |

---

## 📜 Citation

If you use this work in your research, please cite:

```bibtex
@article{mangifranet2026,
  title     = {MangiferaNet: A Lightweight and Intelligent Web-Based Framework 
               for Automated Detection of Mango Leaf Diseases with an 
               In-Depth Comparative Literature Analysis},
  author    = {Subir19},
  year      = {2026},
  url       = {https://github.com/YOUR_USERNAME/MangiferaNet}
}
```

---

## 📝 License

This project is licensed under the **MIT License** — see the [LICENSE](LICENSE) file for details.

---

## 🙏 Acknowledgements

- [MobileNetV2](https://arxiv.org/abs/1801.04381) — Sandler et al., Google Inc.
- [TensorFlow](https://tensorflow.org) & [Keras](https://keras.io)
- [Flask](https://flask.palletsprojects.com)
- [Hugging Face Spaces](https://huggingface.co/spaces) for free hosting

---

<p align="center">Made for sustainable agriculture 🌾</p>
