GTSRB Traffic Sign Classifier
---
A deep learning-based image classification model trained on the German Traffic Sign Recognition Benchmark (GTSRB) dataset. This project uses Convolutional Neural Networks (CNNs) with class-specific data augmentation to achieve high test accuracy and balanced class-wise performance.

Table of Contents
---
Overview

Dataset

Getting The Dataset

Model Architecture

Training Strategy

Augmentation Strategy

Results

Usage

Project Highlights

License



---

Overview

This project explores the development of a CNN for traffic sign classification using the GTSRB dataset. It focuses on:

Achieving >97% test accuracy

Maintaining class-wise recall and precision above 90%

Applying targeted data augmentation to underperforming classes



---

Dataset

The GTSRB dataset consists of over 50,000 images in 43 classes of German traffic signs. Each image varies in lighting, size, and perspective.

Training images: ~39,000

Testing images: ~12,000

Images are resized to 32x32x3

---
📁 Getting the Dataset
This project uses the German Traffic Sign Recognition Benchmark (GTSRB) dataset, available on Kaggle:

👉 Kaggle - GTSRB - German Traffic Sign Recognition Benchmark

---

Model Architecture

3 Convolutional Layers (with ReLU and Batch Normalization)

MaxPooling and Dropout

Fully Connected Layer + Output Layer (43 classes)

Optimized using Adam, loss via CrossEntropyLoss


> See get_cnn_model() in the code for exact architecture.




---

Training Strategy

Dataset split: 80% train / 20% validation

Training on GPU where available

Epochs: 5

Batch size: 64

Input normalization and channel-first tensor formatting



---

Augmentation Strategy

Targeted data augmentation was applied based on class-wise performance analysis across multiple runs. Weak or overfit classes were augmented using:

RandomHorizontalFlip

RandomRotation

ColorJitter (brightness, contrast)


> Augmentation was applied only to selected classes like 0, 40, 30, 23 based on precision/recall analysis.




---

Results

Final Performance:

Test Accuracy: 97.42%

Train Accuracy: ~99.7%

No classes had precision or recall below 85%

Minimal overfitting due to dropout and smart augmentation


Class	Precision	Recall	Notes

0	0.93	1.00	Augmented, stable improvement
20	0.97	0.77	Not augmented in final model
41	0.77	0.94	Needs careful handling



---

Project Highlights

Extensive class-wise analysis using precision/recall

Smart augmentation instead of uniform augmentation

Performance-driven, data-informed development

Multiple model versions with performance tracking


---

License

This project is licensed under the MIT License. See the LICENSE file for more details.


---

Acknowledgements

1. German Traffic Sign Recognition Benchmark (GTSRB)
2. PyTorch for deep learning framework

---

LinkedIn Post

 Connect with me on LinkedIn: https://www.linkedin.com/in/rohit-bangar-24b174305/ 
 Linkedin post : LinkedIn Post
