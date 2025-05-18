# Tomato Leaf Disease Classification using Deep Learning

This project focuses on the classification of plant diseases using image data from the Plant Disease Dataset available on Kaggle. The goal is to develop a model that can accurately identify plant diseases from leaf images using computer vision techniques.

---

## Classification Tomato Plant Disease is crucial for several reasons:
- **🌾 Agricultural Productivity**: The early and accurate identification of tomato leaf diseases helps prevent widespread outbreaks. This is critical for agricultural productivity, as it ensures healthy plant growth and maximizes crop yield.
- **💰 Economic Impact**: Reducing crop losses due to leaf diseases directly supports farmers' financial stability and strengthens the overall agricultural economy, especially in regions where tomatoes are a key cash crop.
- **🍽️ Food Security**: Protecting tomato plants from disease ensures consistent production, which contributes to maintaining a stable and sufficient food supply for local and global consumption.
- **🌱 Environmental Protection**: Efficient disease classification enables targeted and appropriate treatments, reducing the overuse of pesticides and promoting environmentally sustainable farming practices.
- **🧠 Technological Advancement**: Using computer vision and deep learning (e.g., CNN) for disease classification enables faster and more accurate diagnosis, empowering farmers with modern tools for smart agriculture.
- **🔬 Research and Disease Monitoring**: Accurate classification data supports the development of disease-resistant tomato varieties and helps establish systems for early warning and monitoring of disease outbreaks by season or region.
---

## 📁 Dataset

The dataset contains **20,639** images of plant leaves categorized into **15 classes**. These classes represent combinations of plant species and associated diseases, including healthy leaves.
- **Categories**
-Pepper__bell___Bacterial_spot
-Pepper__bell___healthy
-Potato___Early_blight
-Potato___Late_blight
-Potato___healthy
-Tomato_Bacterial_spot
-Tomato_Early_blight
-Tomato_Late_blight
-Tomato_Leaf_Mold
-Tomato_Septoria_leaf_spot
-Tomato_Spider_mites_Two_spotted_spider_mite
-Tomato__Target_Spot
-Tomato__Tomato_YellowLeaf__Curl_Virus
-Tomato__Tomato_mosaic_virus
-Tomato_healthy

- **Format**: `.jpg` images size 256x256 pixel
- **Structure**: Folder-based classification (one folder per class)

---

## ⚙️ Methodology

### 1. Data Preprocessing
- Data Augmentation for classes with < 1000 images
- Normalized pixel values

### 2. Model Architecture
- **Base Model**: Transfer learning using a pre-trained CNN model (e.g., `ResNet50`, `EfficientNetB0`, or `MobileNetV2`)
- Added custom dense layers for classification
- Used softmax activation in the final layer for multi-class classification

### 3. Training
- Split the dataset: 80% for training, 20% for validation
- Optimizer: Adam
- Loss Function: Categorical Crossentropy
- Epochs: 10–25 depending on experiment
- Batch Size: 32

### 4. Evaluation
- Metrics used: Accuracy, Precision, Recall, F1-score
- Confusion matrix analysis to check misclassification

---

## 📊 Results

- **Best Accuracy on Validation Set**: 98.5% (using ResNet50 + augmentation)
- **Overfitting**: Minor; controlled via dropout and augmentation
- **Misclassified Classes**: Often among visually similar diseases like early vs. late blight

Example confusion matrix and accuracy curve (add image if available):

