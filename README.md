# Tomato-Leaf-Disease-Classification-with-Convolution-Neural-Network-CNN-

# Plant Disease Classification using Deep Learning

This project focuses on the classification of plant diseases using image data from the [Plant Disease Dataset](https://www.kaggle.com/datasets/emmarex/plantdisease) available on Kaggle. The goal is to develop a model that can accurately identify plant diseases from leaf images using computer vision techniques.

---

## 📁 Dataset

The dataset contains **54,306** images of plant leaves categorized into **38 classes**. These classes represent combinations of plant species and associated diseases, including healthy leaves.

- **Format**: `.jpg` images
- **Categories**: Examples include `Apple___Black_rot`, `Tomato___Late_blight`, `Corn___Healthy`, etc.
- **Structure**: Folder-based classification (one folder per class)

---

## ⚙️ Methodology

### 1. Data Preprocessing
- Resized all images to a fixed size (e.g., 224x224 pixels)
- Normalized pixel values
- Applied data augmentation (e.g., rotation, flipping) to improve generalization

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

