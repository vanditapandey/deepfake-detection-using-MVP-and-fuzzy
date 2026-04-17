# Deepfake Detection using Multi-View Processing, Dual CNN Models, and Fuzzy Fusion

## Overview

This project implements a deepfake detection system that combines **multi-view image processing**, **two deep learning models (Xception and EfficientNet)**, and a **fuzzy logic-based decision system**.

The goal is to improve robustness by analyzing multiple variations of the same image and leveraging complementary strengths of different architectures.

---

## Key Idea

Instead of relying on a single model or a single image representation, the system:

* Generates multiple transformed versions of an input image
* Passes each version through both models
* Aggregates predictions across views
* Applies weighted fusion
* Uses fuzzy logic to produce the final decision

---

## Workflow

1. **Input Image**

   * Face image is provided from dataset or as a single test input

2. **Multi-View Processing**

   * Original image
   * Flipped image
   * Rotated image
   * Blurred image

3. **Model Inference**

   * Each view is passed through:

     * Xception
     * EfficientNet

4. **Aggregation**

   * Predictions are averaged across all views for each model

5. **Weighted Fusion**

   * Combines outputs from both models using predefined weights

6. **Fuzzy Logic Decision**

   * Interprets model confidence levels
   * Produces final classification: **REAL or FAKE**

---

## Dataset

The project uses the **140k Real and Fake Faces dataset** available on Kaggle.

Structure:

```
real_vs_fake/
    train/
        real/
        fake/
    valid/
        real/
        fake/
    test/
        real/
        fake/
```

---

## Training Process

* Models are initialized with ImageNet weights
* Final classification layers are added
* Training is performed on the training split
* Validation is done using the validation split
* Models are saved after training

---

## Evaluation

The system evaluates performance on the **test dataset** using:

* Confusion Matrix
* Precision
* Recall
* F1-score

This ensures the model is tested on unseen data.

---

## Technologies Used

* Python
* OpenCV
* TensorFlow / Keras
* NumPy
* scikit-learn

---
## Notes

* The system uses transfer learning for efficiency
* Performance depends heavily on dataset quality and balance
* Multi-view processing improves robustness to variations
* Fuzzy logic adds interpretability to the final decision

---

## Future Improvements

* Fine-tune base models instead of freezing layers
* Add data augmentation during training
* Implement region-level localization (heatmaps)
* Replace fuzzy rules with learned fusion strategies

---

## Summary

This project demonstrates a hybrid approach to deepfake detection by combining:

* Deep learning models
* Multi-view analysis
* Rule-based decision logic

It provides a structured and explainable pipeline while maintaining flexibility for further improvements.

---
