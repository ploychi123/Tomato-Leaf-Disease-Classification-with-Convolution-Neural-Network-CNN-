# Tomato Leaf Disease Classification with CNN

This project focuses on the classification of plant diseases using image data from the Plant Disease Dataset available on Kaggle. The goal is to develop a model that can accurately identify plant diseases from leaf images using computer vision techniques.



## 🍅 Classification Tomato Plant Disease is crucial for several reasons:
- **Agricultural Productivity**: The early and accurate identification of tomato leaf diseases helps prevent widespread outbreaks. This is critical for agricultural productivity, as it ensures healthy plant growth and maximizes crop yield.
- **Economic Impact**: Reducing crop losses due to leaf diseases directly supports farmers' financial stability and strengthens the overall agricultural economy, especially in regions where tomatoes are a key cash crop.
- **Food Security**: Protecting tomato plants from disease ensures consistent production, which contributes to maintaining a stable and sufficient food supply for local and global consumption.
- **Environmental Protection**: Efficient disease classification enables targeted and appropriate treatments, reducing the overuse of pesticides and promoting environmentally sustainable farming practices.
- **Technological Advancement**: Using computer vision and deep learning (e.g., CNN) for disease classification enables faster and more accurate diagnosis, empowering farmers with modern tools for smart agriculture.
- **Research and Disease Monitoring**: Accurate classification data supports the development of disease-resistant tomato varieties and helps establish systems for early warning and monitoring of disease outbreaks by season or region.


## 📁 Dataset

The dataset contains **20,639** images of plant leaves categorized into **15 classes**. These classes represent combinations of plant species and associated diseases, including healthy leaves.
- **Categories**
  - Pepper__bell___Bacterial_spot
  - Pepper__bell___healthy
  - Potato___Early_blight
  - Potato___Late_blight
  - Potato___healthy
  - Tomato_Bacterial_spot
  - Tomato_Early_blight
  - Tomato_Late_blight
  - Tomato_Leaf_Mold
  - Tomato_Septoria_leaf_spot
  - Tomato_Spider_mites_Two_spotted_spider_mite
  - Tomato__Target_Spot
  - Tomato__Tomato_YellowLeaf__Curl_Virus
  - Tomato__Tomato_mosaic_virus
  - Tomato_healthy

- **Format**: `.jpg` images size 256x256 pixel
- **Structure**: Folder-based classification (one folder per class)



## ⚙️ Methodology

### 1. Data Preprocessing
- Import Data from Kaggle
- Select 10 Tomato Leaf Disease Classes only
- Cut off each class to 1,000 images max
- Data Augmentation for classes with fewer than 1,000 images
- Split the dataset into Training, Validation, and Test Sets (70/15/15)
- Normalize pixel values to the range [0,1]

### 2. Model Architecture
A custom CNN model was built from scratch with the following layers:
```python
model = Sequential([
    Conv2D(32, (3, 3), activation='relu', input_shape=(150, 150, 3)),
    MaxPooling2D(2, 2),

    Conv2D(64, (3, 3), activation='relu'),
    MaxPooling2D(2, 2),

    Conv2D(128, (3, 3), activation='relu'),
    MaxPooling2D(2, 2),

    Flatten(),
    Dropout(0.5),
    Dense(128, activation='relu'),
    Dense(train_generator.num_classes, activation='softmax')
])
```
- Total convolutional layers: 3
- Activation function: ReLU
- Output: Softmax layer matching number of disease classes

### 3. Training

- Optimizer: Adam
- Loss Function: Categorical Crossentropy
- Epochs: 100 
- Batch Size: 32

### 4. Evaluation
- Metrics used: Accuracy, Precision, Recall, F1-score
- Confusion matrix analysis to check misclassification



## 📊 Results

- **Best Accuracy on Validation Set**: 89.29%
- **Test Set Accuracy**: 91%
- **Misclassified Classes**: Often occurred between visually similar diseases like Early vs. Late Blight or Spider Mites vs. Septoria Leaf Spot.



## 🔍 Observations from Evaluation:
- Tomato_Bacterial_spot and Tomato_Tomato_YellowLeaf_Curl_Virus achieved very high precision and recall (close to or above 95%), indicating the model performed well in identifying clear visual symptoms.
- Tomato_Early_blight and Tomato_Late_blight had lower precision and recall (around 84-90%), likely due to similar visual features, making them harder to distinguish.
- Tomato_Septoria_leaf_spot and Spider_mites_Two_spotted_spider_mite also showed lower performance, potentially due to overlapping symptom patterns like spots and lesions.
- Tomato_healthy was correctly identified in most cases, with a 98% recall and 95% precision.
