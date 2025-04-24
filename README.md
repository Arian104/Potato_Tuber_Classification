# Potato Tuber Disease Classification using Deep Learning and Grad-CAM

## Introduction

Potato is one of the most widely cultivated and consumed vegetables globally. It is a vital source of food, income, and livelihood for millions of farmers, especially in developing countries. Among the different types of potato production methods, **potted potato plants**—grown in controlled environments like greenhouses or small-scale home setups—have become increasingly popular. These systems help farmers manage soil conditions, monitor growth, and reduce pest exposure.

However, even in such controlled environments, **tuber diseases** such as **blackspot bruising, brown rot, dry rot, and soft rot** can affect crop yield and quality significantly. Manual inspection is time-consuming and prone to human error. Here, deep learning-based **image classification** provides an efficient, scalable solution for disease identification.

This project leverages CNNs and explainable AI to classify tuber diseases with high accuracy and interpretability.

## Dataset and Classes

The dataset is divided into:
- **Training**: 70%
- **Validation**: 15%
- **Testing**: 15%

Classes:
- Blackspot Bruising Disease
- Healthy Potato
- Potato Brown Rot Disease
- Potato Dry Rot Disease
- Potato Soft Rot Disease

## Models Used

### 1. EfficientNetV2B0
- **How it works**: Scales network depth, width, and resolution using a compound coefficient. It includes fused MBConv blocks for faster and more efficient learning.
- **Why chosen**: Lightweight yet powerful; delivers state-of-the-art results with fewer parameters.
- **Efficiency**: Achieved 98.48% test accuracy with an F1-score of 0.98.

### 2. DenseNet121
- **Working principle**: Each layer receives input from all previous layers (dense connections), which improves feature propagation.
- **Reason for selection**: Effective in learning subtle features of diseases with fewer training epochs.
- **Performance**: Test accuracy of 97.72%, F1-score 0.98.

### 3. Xception
- **How it works**: Utilizes depthwise separable convolutions, allowing better model efficiency and deeper architecture.
- **Why chosen**: Excellent at learning abstract patterns from complex tuber textures.
- **Efficiency**: Reached 97.53% accuracy with strong generalization.

### 4. InceptionResNetV2
- **Architecture**: Combines the Inception module with residual connections, enabling very deep networks to train efficiently.
- **Why chosen**: Captures multi-scale features and mitigates vanishing gradients.
- **Performance**: Delivered 93.55% accuracy.

### 5. NASNetMobile
- **How it works**: Designed through neural architecture search (NAS), this model balances efficiency and accuracy for mobile deployments.
- **Use case**: Ideal for real-time classification on edge devices.
- **Result**: 87.10% accuracy, slightly lower but efficient on lightweight setups.

## Explainable AI with Grad-CAM

To understand and visualize the model’s decision-making process, **Grad-CAM (Gradient-weighted Class Activation Mapping)** is applied. It highlights the regions of the image that were important for the classification, offering transparency and trust—critical for agricultural applications.

## Result Summary

| Model             | Accuracy | Precision | Recall | F1-Score |
|------------------|----------|-----------|--------|----------|
| EfficientNetV2B0 | 98.48%   | 0.98      | 0.98   | 0.98     |
| DenseNet121      | 97.72%   | 0.98      | 0.98   | 0.98     |
| Xception         | 97.53%   | 0.98      | 0.98   | 0.98     |
| InceptionResNetV2| 93.55%   | 0.94      | 0.94   | 0.94     |
| NASNetMobile     | 87.10%   | 0.91      | 0.87   | 0.88     |

## Use Cases and Future Scope

- Integration into grading machines to sort diseased tubers.
- Real-time camera-based disease detection in warehouses.
- Training models for early-stage (immature tubers) disease identification.
- Extending to nutrient or pesticide deficiency detection.
