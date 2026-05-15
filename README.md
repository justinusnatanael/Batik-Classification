# Batik Classification – Indonesian Batik Motif Classification Using Deep Learning

## Overview
This project focuses on classifying Indonesian batik motifs using deep learning and computer vision techniques. The objective of this project is to develop an automated image classification system capable of recognizing different batik patterns, specifically Batik Bali, Batik Keraton, and Batik Betawi.

By utilizing Convolutional Neural Networks (CNN) and transfer learning methods, this project explores how deep learning models can effectively perform image recognition tasks while preserving and promoting Indonesian cultural heritage through technology.

---

# Workflow

## Collecting Data
The dataset used in this project was obtained from Kaggle using the dataset **"Indonesian Batik Motifs"** curated by DionisiusDH.

The original dataset contains 20 folders of Indonesian batik motif images. For this project, three batik classes were selected:
- Batik Bali
- Batik Keraton
- Batik Betawi

Each class contains approximately 50 high-resolution batik images used for training and evaluation.

---

## Data Preprocessing
Several preprocessing techniques were applied before model training:

- Image resizing to 256x256 pixels
- Pixel normalization using:
```python
rescale = 1./255
```

- Data augmentation to improve model generalization and reduce overfitting:
  - Random rotation
  - Brightness adjustment
  - Contrast transformation
  - Random zoom
  - Horizontal flipping
  - Vertical flipping

The dataset was then split into training, validation, and testing sets.

---

# Modelling

## 1. Scratch CNN Model
A custom Convolutional Neural Network (CNN) architecture was developed using TensorFlow and Keras. The model includes:
- Conv2D layers
- MaxPooling layers
- Dense layers
- Dropout regularization

The model was trained from scratch using the batik dataset.

---

## 2. Transfer Learning Model
The second approach uses transfer learning with **MobileNetV2** as the pretrained base model.

The implementation includes:
- Frozen pretrained layers
- GlobalAveragePooling2D
- Custom dense classification layers
- Fine-tuning for batik image classification

Transfer learning was implemented to improve classification performance on a relatively small dataset.

---

# Hyperparameter Tuning
Both models were experimented with hyperparameter tuning to improve performance, including:
- Learning rate adjustment
- Batch size tuning
- Epoch optimization
- Dropout configuration

---

# Accuracy Results
Model accuracy was evaluated using test data consisting of approximately 10% of the overall dataset.

| Model | Before Tuning | After Tuning |
|---|---|---|
| Scratch CNN | 43% | 40% |
| MobileNetV2 Transfer Learning | 27% | 70% |

## Key Findings
- Transfer learning significantly improved classification accuracy compared to the scratch CNN model.
- MobileNetV2 achieved the best performance after hyperparameter tuning.
- Data augmentation helped reduce overfitting and improved model generalization.
- Pretrained architectures are more effective for small image datasets.

---

# Technologies Used
- Python
- TensorFlow
- Keras
- NumPy
- Matplotlib
- OpenCV
- Scikit-learn

---

# Learning Outcomes
Through this project, several deep learning and computer vision concepts were explored, including:
- CNN architecture implementation
- Transfer learning techniques
- Image preprocessing and augmentation
- Hyperparameter tuning
- Image classification workflows
- Model evaluation and visualization

---

# Future Improvements
Possible future improvements include:
- Adding more Indonesian batik classes
- Using larger image datasets
- Implementing advanced architectures such as EfficientNet or ResNet
- Deploying the model into a web or mobile application
- Real-time batik classification using webcam integration

---

# Conclusion
This project demonstrates the implementation of deep learning for Indonesian batik motif classification. The experimental results show that transfer learning using MobileNetV2 significantly outperformed the CNN model trained from scratch, especially when working with limited datasets.

Overall, this project highlights the potential of artificial intelligence and computer vision technologies in supporting cultural preservation and automated image recognition systems.
