# 🧠 Task 1: Edge AI Prototype – Report

## Objective

This task demonstrates how to train a lightweight image classification model using TensorFlow/Keras and deploy it using TensorFlow Lite (TFLite) for Edge AI use cases. The goal is to simulate a model that can classify recyclable items in real-time on edge devices.

---

## Model Description

- **Framework**: TensorFlow 2.x (with Keras API)
- **Dataset**: CIFAR-10 (used as a placeholder for recyclable items)
- **Input Shape**: 32x32 RGB images
- **Model Architecture**:
  - Conv2D(16) → MaxPooling2D
  - Conv2D(32) → MaxPooling2D
  - Flatten → Dense(64) → Dense(10 softmax)
- **Total Parameters**: ~40,000 (suitable for deployment on small devices)

---

## Training Results

- **Epochs**: 3  
- **Validation Split**: 10%  
- **Final Test Accuracy**: ~0.68 (on CIFAR-10)  
- **Loss Function**: Categorical Crossentropy  
- **Optimizer**: Adam  

---

## TFLite Conversion

The trained Keras model was successfully converted to a `.tflite` model using `tf.lite.TFLiteConverter`. This model is now optimized for inference on resource-constrained edge devices such as Raspberry Pi, smartphones, or microcontrollers.

---

## Benefits of Edge AI

- **Reduced Latency**: Processing happens on the device—no need for round-trip to cloud.
- **Improved Privacy**: Data stays local, reducing exposure risk.
- **Offline Functionality**: Enables real-time inference even in low/no network zones.
- **Lower Bandwidth Usage**: No need to upload images to the cloud for classification.

---

## Deployment Steps Summary

1. Train the CNN model using TensorFlow/Keras.
2. Convert the model to `.tflite` format using TFLiteConverter.
3. Deploy the `.tflite` model to an edge device or emulator.
4. Use TensorFlow Lite Interpreter to run inference on-device.

---

## Next Steps

- Replace CIFAR-10 with a custom dataset of recyclable items for better relevance.
- Add quantization for further model size reduction.
- Integrate with camera input for real-time use on Raspberry Pi or Android.
